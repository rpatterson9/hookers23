<template>
  <div class="ui container">
    <div v-if="loaded" >
      <div class="ui basic segment fluid">
        <h2 class="ui huge header">
          <i class="far fa-user"></i>
          Account
        </h2>
      </div>
      <!-- Account details -->
      <div class="ui segment raised">
        <div class="ui stackable grid equal width center aligned">
          <div class="column">
            <h3 class="ui header"><i class="far fa-user"></i> <b>Address</b></h3>
            {{ currentAddress }}
          </div>
          <div class="column">
            <h3 class="ui header"><i class="fa fa-balance-scale"></i> <b>Balance</b></h3>
            {{ balance }} Ether
              <span class="ui red tiny compact button"
                  :class="{ 'disabled': balance === '0' }"
                  @click.prevent="withdraw()">
                  Withdraw
              </span>
          </div>
        </div>
        <div class="ui basic segment stackable grid equal width center aligned">
            <div class="column">
              <h4 class="ui header"><i class="far fa-address-card"></i> <b>Bought</b></h4>
              {{ boughtCards.length }}
            </div>
            <div class="column">
              <h4 class="ui header"><i class="fa fa-dollar-sign"></i> <b>In sale</b></h4>
              {{ saleCards.length }}
            </div>
            <div class="column">
              <h4 class="ui header"><i class="fa fa-arrow-up"></i><i class="fa fa-key"></i> <b>Rented out</b></h4>
              {{ leasingCards.length }}
            </div>
            <div class="column">
              <h4 class="ui header"><i class="fa fa-arrow-down"></i><i class="fa fa-key"></i> <b>Rent</b></h4>
              {{ rentingCards.length }}
            </div>
        </div>
      </div>
      <!-- Cards -->
      <div class="ui basic segment fluid">
        <div class="ui grid equal width">
          <div class="column">
            <h2 class="ui header">
            <i class="far fa-address-card"></i>
              Cards <small>({{ accountCards.length }})</small>
            </h2>
          </div>
          <!--
          <div class="column right aligned">
            <div class="ui simple dropdown item">
              <i class="icon plus"></i>
              <i class="dropdown icon"></i>
              <div class="menu">
                <div class="item">Applications</div>
                <div class="item">International Students</div>
                <div class="item">Scholarships</div>
              </div>
            </div>
          </div>
          -->
        </div>
      </div>
      <div v-if="accountCards.length > 0" class="ui container">
        <div class="ui link four stackable cards">
          <card v-for="card in accountCards" :key="card.id" :index="card.id"></card>
        </div>
      </div>
      <div v-if="accountCards.length === 0" class="ui segment center aligned raised">
        No cards
      </div>
    </div>
    <!-- Loader -->
    <loader v-if="!loaded && !networkUnknown" />
    <!-- Wrong network -->
    <div v-if="networkUnknown" class="ui segment center aligned">
      <img class="ui image centered tiny" :src="require('@/assets/images/metamask.png')" /><br />
      Select <b>Main Ethereum Network</b> in MetaMask to display your account
    </div>
  </div>
</template>

<script>
import web3 from 'web3'
import Card from './Card'
import Loader from '@/components/layouts/Loader'
import { successNotification, transactionDeniedNotif } from '@/api'
import config from '@/config'

export default {
  name: 'account',
  components: {
    Loader,
    Card
  },
  data () {
    return {
      balance: '0'
    }
  },
  watch: {
    currentAddress (value) {
      this.getBalance()
    },
    loaded (value) {
      if (value) this.getBalance()
    }
  },
  computed: {
    loaded () {
      return (this.$store.getters.cards.length >= config.cardsNumber)
    },
    networkUnknown () {
      return this.$store.getters.networkUnknown
    },
    accountCards () {
      return this.$store.getters.cards.filter(c => c.isOwner() || c.isWrappedOwner() ||
              (c.inLeasing() && this.currentAddress === c.lastLease.tenant)) // if current address rent this card
    },
    contract () {
      return this.$store.getters.contract
    },
    currentAddress () {
      return this.$store.getters.currentAddress
    },
    leasingCards () {
      return this.$store.getters.cards.filter(c => (c.inLeasing() && this.currentAddress === c.owner))
    },
    saleCards () {
      return this.$store.getters.cards.filter(c => c.availableBuy && this.currentAddress === c.owner)
    },
    rentingCards () {
      return this.$store.getters.cards.filter(c => (c.inLeasing() && this.currentAddress === c.lastLease.tenant))
    },
    boughtCards () {
      return this.$store.getters.cards.filter(c => c.isOwner())
    }
  },
  methods: {
    getBalance () {
      this.contract.methods.getBalance()
        .call({ from: this.currentAddress })
        .then((balance) => {
          this.balance = web3.utils.fromWei(balance, 'ether')
        })
    },
    withdraw () {
      this.contract.methods.withdraw()
        .send({ from: this.currentAddress })
        .then((res) => {
          this.balance = '0'
          successNotification(`Balance withdrawed !`)
        })
        .catch((err) => {
          console.log(err.message)
          transactionDeniedNotif(err.message)
        })
    }
  },
  mounted () {
    if (this.contract != null) {
      this.getBalance()
    }
  }
}
</script>

<style scoped>
.cards {
  margin-top: 0.3em !important;
}
.container {
  max-width: 978px !important;
}
.row {
  padding-bottom: 2.5em !important;
  padding-top: 2.5em !important;
}
h3 {
  margin-bottom: 0.7em !important;
}
</style>
