<template>
  <div class="ui container">
    <div class="ui basic segment fluid">
      <h1 class="ui header">
        <i class="fa fa-question"></i>
        FAQ
      </h1>
    </div>

    <div class="ui segment raised">
      <div class="ui link selection animated list">
        <div class="item">
          MorphCards
          <div class="list">
            <router-link class="item" :to="{ name: 'FAQ', hash: '#how-it-works' }">How it works ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#whats-cool' }">So, what's the deal ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#what-do-i-need' }">What do I need ?</router-link>
          </div>
        </div>
        <div class="item">
          Cards
          <div class="list">
            <router-link class="item" :to="{ name: 'FAQ', hash: '#buy-card' }" >How do I buy a card ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#sell-card' }" >How do I sell a card ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#lease-card' }" >
              How do I lease a card ?
              <div class="list">
                <router-link class="item" :to="{ name: 'FAQ', hash: '#lease-card-tenant' }" >As a tenant</router-link>
                <router-link class="item" :to="{ name: 'FAQ', hash: '#lease-card-lessor' }" >As a lessor</router-link>
              </div>
            </router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#edit-card' }" >How can I edit a card ? </router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#transfer-card-owner' }" >Can I transfer my card to another address ? </router-link>
          </div>
        </div>
        <div class="item">
          Miscellaneous
          <div class="list">
            <router-link class="item" :to="{ name: 'FAQ', hash: '#fees' }">Is there any fees ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#what-is-giveth' }">What is Giveth.io ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#who-are-you' }">Who are you ?</router-link>
            <router-link class="item" :to="{ name: 'FAQ', hash: '#projects-money' }">What will you do with the money ? </router-link>
          </div>
        </div>
      </div>
    </div>
    <div class="ui segment raised">
      <h2 class="ui header" id="how-it-works">
        How it works ?
      </h2>
      <p>MorphCards  let you <router-link :to="{ name: 'FAQ', hash: '#buy-card' }" >buy</router-link>, <router-link :to="{ name: 'FAQ', hash: '#lease-card' }" >lease</router-link> and <router-link :to="{ name: 'FAQ', hash: '#sell-card' }" >sell</router-link> cards.
      MorphCards homepage is filled with cards ranked from 1 to 100. Each card is sold at a price related to its rank, the card #1 is initially sold at 1 Ether and card #100 is set at 0.01 Ether.
      A card is made from a descriptive title, a redirection URL and an image set by the card owner.
      For each card sold during the initial sale, <b>10% of the amount is reversed to <router-link :to="{ name: 'FAQ', hash: '#what-is-giveth' }" >Giveth</router-link></b> !
      </p>
      <p>If no cards are available to buy, you probably can rent one. You'll pay to the card owner a fixed amount of Ether to display
      your details for a pre-determined duration.</p>
      <div class="ui stackable grid">
        <div class="column ten wide">
          <p>Once you purchased a card, it belongs to <b>you</b>. From here you have multiple options :</p>
          <ul>
            <li><b><router-link :to="{ name: 'FAQ', hash: '#lease-card' }" >Rent</router-link></b> it out to someone for a fixed price and duration</li>
            <li><b><router-link :to="{ name: 'FAQ', hash: '#sell-card' }" >Sell</router-link></b> it to a fixed price</li>
            <li><b><router-link class="item" :to="{ name: 'FAQ', hash: '#edit-card' }" >Edit</router-link></b> your card details</li>
            <li><b>Leave</b> it as it is</li>
          </ul>
          <p>
            You can <b>rent out</b> your card to someone willing to rent it. As owner, you will get the total rent amount beforehand.
            During the lease, the card will display and redirect to the details provided by the tenant. Once the lease end,
            the card display your details again.
          </p>
          <p>
            <b>Selling</b> a card is as simple as setting a sale price and voilà, your card can now be bought by anyone. The ownership
            will be transferred to the first buyer and you will be credited of the sale amount !
          </p>
          <p>
            You can <b>edit</b> your cards at any time in the card <i class="fa fa-cogs"></i> <b>Settings</b>
            (click on card position <span class="ui tiny circular label card-id-label" :data-tooltip="`View card #15 details`" data-inverted=""><b>15</b></span>
            to display its details and settings). From there, you may also <b>transfer the ownership</b> of your card.
          </p>
          <p>
            Finally, you can just <b>leave</b> your card(s) with your details and strut around that you own one (or more !) of 100 unique cards.
          </p>
        </div>
        <div class="column six wide center">
          <!-- Card buy demo -->
          <div class="ui link cards">
            <div class="ui centered card raised">
              <div class="ui fluid image">
                <div class="ui floating right circular label card-id-label" :data-tooltip="`View card #6 details`" data-inverted="">
                    <b>15</b>
                </div>
                <img class="card-image" :src="require('@/assets/images/demo-card-squirrel.png')">
              </div>
              <div class="content">
                <div class="ui header">
                  Card #15
                </div>
                <div class="meta">
                  squirrel.io
                </div>
              </div>
              <div class="extra content">
                <div class="ui grid equal width center aligned">
                  <div class="column" :data-tooltip="`Owned by 0x627306090abaB3A6e1400e9345bC60c78a8BEf57`" data-inverted="">
                    <i class="fa fa-user"></i>
                    0x627306090ab...
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="ui segment basic center aligned card-description">Card #15 is owned by 0x627306090ab...</div>
        </div>
      </div>

      <h2 class="ui header" id="whats-cool">
        So, what's the deal ?
      </h2>
      <p>Although MorphCards looks like a regular website, it's not one, it's a Decentralized Applications (ÐApps). Cards are not loaded from our database (we do not host anything) but instead directly loaded from the Ethereum blockchain.
      This blockchain acts like a decentralized database where everyone can see its state and cannot be tampered by anyone. Once you acquired a card, it is written in
      the blockchain and it remains forever yours.
      </p>
      <p>
      The other cool stuff is that you can check the logic behind WeiCard by auditing the Smart Contract. You can have a look at the <a target="_blank" href="https://etherscan.io/address/0x7f57292bf494a8c9342d37395d1378a65d59c499">contract on Etherscan</a>
      or the front-end hosted on <a target="_blank" href="https://github.com/willdn/MorphCards"><i class="fab fa-github"></i> Github</a>.
      </p>

      <h2 class="ui header" id="what-do-i-need">
        What do I need ?
      </h2>
      <p>You only need a browser to view cards and cards details. However, you will need <a href="https://metamask.io/">MetaMask</a> to buy, lease and sell cards.
      MetaMask is a browser (<i class="fab fa-chrome"></i> Chrome and <i class="fab fa-firefox"></i> Firefox) plugin that bridge the Ethereum blockchain
      and is the easiest way to interact with Smart Contract.</p>
      <p>
        This plugin provides a wallet where you can send some Ether (Ξ) in order to execute operations. This plugin is your only <b>login access</b> to buy, lease and sell cards !
        Thus, there is no registration nor login form, just install and unlock a wallet on MetaMask and you have now access to every MorphCards features.
      </p>
      <p>
        The following video gives an introduction and a setup guide for MetaMask :
      </p>

      <div class="ui segment basic center aligned">
        <iframe width="560" height="315" src="https://www.youtube.com/embed/6Gf_kRE4MJU?rel=0" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>
      </div>
    </div>
    <!--
      CARDS
     -->
    <div class="ui segment raised">
      <h2 class="ui header" id="buy-card">
        How do I buy a card ?
      </h2>
      <div class="ui stackable grid">
        <div class="column ten wide">
          <p>Cards available to purchase have a <span class="ui green tiny label"><i class="fa fa-shopping-cart"></i> Buy</span> ribbon in their top left corner.
          In order to buy this card, you can either click on this ribbon or the card footer
          <i class="fa fa-shopping-cart"></i> <b>Buy</b> (< <i>Price</i> > Ξ).
          </p>
          <p>
          You will need to provide 3 things :
            <div class="ui list buy-list">
              <div class="item"><i class="fa fa-bars"></i> <b>Title: </b> Title of your card, it can describe anything you want.
              Title must be less than 40 characters and greater than 3.</div><br />
              <div class="item"><i class="fa fa-link"></i> <b>URL: </b> URL to redirect to when visitors click on your card.</div><br />
              <div class="item"><i class="far fa-image"></i> <b>Image: </b> URL of the image you want to display within the card.
              Image can be of any types supported by browsers (<i>e.g.</i> PNG, JPG, SVG <i>etc.</i>).
              Try to use an image as lightweight as possible.</div>
            </div>
          <div class="ui orange message">
            <b>Note</b> : the more your URL and image URL are longer, the more<b> you are paying</b> in fee !
            This is inherent to the Ethereum blockchain design.
          </div>
          </p>
        </div>
        <div class="column six wide">
          <!-- Card buy demo -->
          <div class="ui link cards">
            <div class="ui centered card raised">
              <div class="ui fluid image">
                <div class="ui floating right circular label card-id-label" :data-tooltip="`View card #6 details`" data-inverted="">
                    <b>6</b>
                </div>
                <img class="card-image" :src="require('@/assets/images/demo-card-cat.png')">
                <!-- Ribbon available buy -->
                <a class="ui green tiny left ribbon label">
                  <i class="fa fa-shopping-cart"></i>
                  <b>Buy</b>
                </a>
              </div>
              <div class="content">
                <div class="ui header">
                  Card #6
                </div>
                <div class="meta">
                  kitty.io
                </div>
              </div>
              <div class="extra content">
                <div class="ui grid equal width center aligned">
                  <div class="column green-hover"
                      :data-tooltip="`Buy card #6 at 0.95 Ξ`" data-inverted="">
                    <i class="fa fa-shopping-cart"></i>
                    Buy (<b>0.95 Ξ</b>)
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="ui segment basic center aligned card-description">This cute little card is available to buy for 0.95 Ξ</div>
        </div>
      </div>

      <h2 class="ui header" id="sell-card">
        How do I sell a card ?
      </h2>
      <div class="ui stackable grid">
        <div class="column ten wide">
          <p>
            You obviously need to <router-link :to="{ name: 'FAQ', hash: '#buy-card' }" >own a card</router-link> in order to sell one.
            If you want to put one of yours on sale, select <i class="fa fa-dollar-sign"></i> <b>Sell</b> in the footer of a card or access
            <i class="fa fa-cogs"></i> <b>Settings</b> > <i class="fa fa-dollar-sign"></i> <b>Sell</b> in card details page.
          </p>
          <p>
            You just have to set the price you want it to be sold. Your card will now be listed as on sale, the ownership
            of your card will be transferred to the first buyer. You will then be credited of the transaction amount. <i>Note :
            MorphCards take a 1% cut on this transaction.</i>
          </p>
          <p>
            Card may be sold even if they are leased, as you have already been credited of the total lease amount. You are also able to
            <router-link :to="{ name: 'FAQ', hash: '#edit-card' }" >edit</router-link> them, your updated details will be displayed once lease
            is over.
          </p>
          <p>
            If you changed your mind and want to keep your card, you can cancel the card sale by hitting <br />
            <i class="fa fa-times"></i> <b>Cancel sale </b> (<i> < Card sale price ></i> Ξ) in card footer or card <i class="fa fa-cogs"></i> <b>Settings</b>.
          </p>
        </div>
        <div class="column six wide">
          <!-- Card buy demo -->
          <div class="ui link cards">
            <div class="ui centered card raised">
              <div class="ui fluid image">
                <div class="ui floating right circular label teal" :data-tooltip="`View card #99 details`" data-inverted="">
                    <b>99</b>
                </div>
                <img class="card-image" :src="require('@/assets/images/demo-card-fox.png')">
              </div>
              <div class="content">
                <div class="ui header">
                  Card #99
                </div>
                <div class="meta">
                  fox.io
                </div>
              </div>
              <div class="extra content">
                <div class="ui grid equal width center aligned">
                  <div class="column green-hover" data-tooltip="Sell card #99" data-inverted="">
                    <i class="fa fa-dollar-sign"></i>
                    Sell
                  </div>
                  <div class="column orange-hover" data-tooltip="Rent out card #99" data-inverted="">
                    <i class="fa fa-key"></i>
                    Rent out
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="ui segment basic center aligned card-description">Cards you own have a teal position label
            <span class="ui tiny circular label teal"><b>99</b></span>
          </div>
        </div>
      </div>

      <h2 class="ui header" id="lease-card">
        How do I lease a card ?
      </h2>
      <h3 class="ui header" id="lease-card-tenant">> As tenant</h3>
      <div class="ui stackable grid">
        <div class="column six wide">
          <!-- Card tenant lease -->
          <div class="ui link cards">
            <div class="ui centered card raised">
              <div class="ui fluid image">
                <div class="ui floating right circular label card-id-label" :data-tooltip="`View card #34 details`" data-inverted="">
                    <b>34</b>
                </div>
                <img class="card-image" :src="require('@/assets/images/demo-card-dog.png')">
               <!-- Ribbon available buy -->
                <a class="ui orange tiny left ribbon label">
                  <i class="fa fa-key"></i>
                  <b>Lease</b>
                </a>
              </div>
              <div class="content">
                <div class="ui header">
                  Card #34
                </div>
                <div class="meta">
                  dog.io
                </div>
              </div>
              <div class="extra content">
                <div class="ui grid equal width center aligned">
                  <div class="column green-hover"
                      :data-tooltip="`Lease card #34 for 0.75 Ξ until ${lease1EstimatedTime.format('LL')}`" data-inverted="">
                    <i class="fa fa-key"></i>
                    <b>0.75 Ξ</b> / 1 000 000 blocks
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="ui segment basic center aligned card-description">Card #34 is available for a lease at a total amount of 0.75 Ξ for
            1 000 000 blocks.</div>
        </div>
        <div class="column ten wide">
          <p>Cards available to rent have a <span class="ui orange tiny label"><i class="fa fa-key"></i> Lease</span> ribbon in their top left corner.
          Just as cards listed on sale, you can either click on this ribbon or the card footer
          <i class="fa fa-key"></i> < <i>Total amount</i> > Ξ / < <i>Block duration</i> >.
          </p>
          <p>
            Details of the lease are displayed in a table similar as the following :
          </p>
          <!-- Lease details -->
          <div class="ui segment basic grid equal width center aligned">
            <div class="column">
              <h3 class="ui header">Ξ Total Amount</h3>
              <b>0.75</b> Ether
            </div>
            <div class="column">
              <h3 class="ui header"><i class="far fa-clock"></i> Duration</h3>
              <b>1 000 000</b> blocks<br />
              {{ lease1EstimatedTime.fromNow() }}
              <span :data-tooltip="`Based on a 15 sec average block time : ${lease1EstimatedTime.format('LL')}`" data-inverted="">
              <i class="fa fa-question-circle"></i>
              </span>
            </div>
            <div class="column" style="word-wrap: break-word;">
              <h3 class="ui header"><i class="far fa-user"></i>Lessor</h3>
              <b>0x627306090abaB3A6e1400e9345bC60c78a8BEf57</b>
            </div>
          </div>
          <p>
            Where the <b>Ξ Total Amount</b> is the product of the <b>lease duration</b> and the <b>price per block</b>, this is paid beforehand by the
            tenant to the lessor. The <i class="far fa-clock"></i> <b>Duration</b> column display the duration of the lease in blocks. At the moment, 1 block &asymp; 15 seconds (<i>e.g.</i> 1 000 000 blocks is approximately 6 months).
            <i class="far fa-user"></i><b>Lessor</b> column display the current owner of the card. During lease offer creation, he set a fixed
            <b>price per block</b> in Wei (1 Ether = 10<sup>18</sup> Wei).
          </p>
        </div>
      </div>
      <br />
      <p>
        You will have to fill the lease form and provide a title, a redirection URL and an image for your rental card.
        Check the <router-link :to="{ name: 'FAQ', hash: '#buy-card' }" >How do I buy a card ?</router-link> section to get more details on those fields.
        Once you submitted the rental form you will be requested to pay the <b>Ξ Total Amount</b> to the <i class="far fa-user"></i><b>Lessor</b>
        , the card you just rented will then display the details you provided until the <i class="far fa-clock"></i> <b>Duration</b> is over.
      </p>


      <h3 class="ui header" id="lease-card-lessor">> As lessor</h3>
      <div class="ui stackable grid">
        <div class="column ten wide">
          <p>
            As a card owner, you are able to rent it out at a fixed price for a determined duration. Cards eligible to rent out has a
            <i class="fa fa-key"></i> <b>Rent out</b> button displayed in their footer. You also can set a card to rent by accessing its
            details page and select <i class="fa fa-cogs"></i> <b>Settings</b> > <i class="fa fa-key"></i> <b>Rent out</b>.
          </p>
          <p>
            You will be asked to enter the amount per block in Wei. This amount represents the price you are asking to lease
            your card for each block mined on the network. The duration field is the number of blocks you want to rent out your card, starting
            at the block number when tenant sign the deal.
          </p>
          <p>
            Considering an average block generation time of 15 seconds, 6 000 blocks
            is a day and 1 000 000 blocks is approximately 6 months. The total amount is the product of the block duration and amount per block, this
            total amount should be greater than 0.005 Ξ. <i>Note : MorphCards take a 1% cut on the lease total amount.</i>
          </p>
          <p>
            You can cancel rent out by selecting <i class="fa fa-times"></i> <b>Cancel rent out</b> in card footer or in card
            <i class="fa fa-cogs"></i> <b>Settings</b> > <i class="fa fa-times"></i> <b>Cancel rent out</b>.
          </p>
        </div>
        <div class="column six wide">
          <!-- Card buy demo -->
          <div class="ui link cards">
            <div class="ui centered card raised">
              <div class="ui fluid image">
                <div class="ui floating right circular label teal" :data-tooltip="`View card #99 details`" data-inverted="">
                    <b>78</b>
                </div>
                <img class="card-image" :src="require('@/assets/images/demo-card-bunny.png')">
              </div>
              <div class="content">
                <div class="ui header">
                  Card #78
                </div>
                <div class="meta">
                  bunny.io
                </div>
              </div>
              <div class="extra content">
                <div class="ui grid equal width center aligned">
                  <div class="column green-hover" data-tooltip="Sell card #78" data-inverted="">
                    <i class="fa fa-dollar-sign"></i>
                    Sell
                  </div>
                  <div class="column orange-hover" data-tooltip="Rent out card #78" data-inverted="">
                    <i class="fa fa-key"></i>
                    Rent out
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <h2 class="ui header" id="edit-card">
        How can I edit a card ?
      </h2>
      <p>
        If you need to update some or all the details of your card, you are able to change them by accessing the card details page and
        select <i class="fa fa-cogs"></i> <b>Settings</b> > <i class="fa fa-wrench"></i> <b>Edit</b>. From there are you can
        edit the card's title, URL and image.
      </p>

      <h2 class="ui header" id="transfer-card-owner">
        Can I transfer my card to another address ?
      </h2>
      <p>To transfer a card ownership to another address, go to card details page and select
         <i class="fa fa-cogs"></i> <b>Settings</b> > <i class="fa fa-exchange-alt"></i> <b>Transfer</b>.
         You will then be prompted to enter the address of the new card owner. This can be used if the account owning the cards has been
         compromised.
      </p>
      <div class="ui orange message">
        <b>Note</b> : we strongly encourage to double-check the recipient address. If you transferred to an address of which you do not own keys,
        consider your card as <b>lost</b>.
      </div>
    </div>

    <div class="ui segment raised">
      <h2 class="ui header" id="fees">
        Is there any fees ?
      </h2>
      <p>Storing or updating data on the blockchain require a fee. Thus, managing your card (<i>i.e.</i> sell it, edit it etc...), require you
         to pay a small fee to those who maintain the blockchain. You can set the maximal fee you want to pay for, as so, you can set a very low
         fee if you accept that your operation take more time.</p>
      <p>
        Otherwise, there is a 1% fee on each card transaction (sell or lease). We are proud to reverse 10% of the profits generated by the initial cards sales
        to Giveth. Note that this 10% cut is only applied to the initial sale and will not be subtracted to your profits from selling or leasing cards.
      </p>

      <h2 class="ui header" id="what-is-giveth">
        What is Giveth ?
      </h2>
      <p>
        <a target="_blank" href="https://giveth.io/">Giveth</a> is an Open-Source Platform for building Decentralized Altruistic Communities (DAC).
      </p>
      <div class="ui basic segment">
        <q>
          Giveth is re-engineering charitable giving, by creating an entirely free, open-source platform, built on the Ethereum Blockchain.
          Our system cuts out bureaucracy and enables nonprofits to create a high level of transparency and accountability towards Givers.
          At any point until the moment funds are locked, a Giver can decide to withdraw them.
        </q>
      </div>
      <p> You can learn more on Giveth <a target="_blank" href="https://medium.com/giveth/what-is-the-future-of-giving-d50446b0a0e4">here</a>.</p>

      <h2 class="ui header" id="who-are-you">
        Who are you ?
      </h2>
      <p>I'm a Computer Science student from Belgium. I'm into blockchain technology since early 2017 and this is my first Smart Contract
        published on the Ethereum blockchain !
      </p>

      <h2 class="ui header" id="projects-money">
        What will you do with the money ?
      </h2>
      <p>I have other projects on the Ethereum blockchain, the profits made by MorphCards will help fund them. It will also be used
        to invest in other blockchain related projects.
      </p>
    </div>
  </div>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'faq',
  data () {
    return {
    }
  },
  computed: {
    lease1EstimatedTime () {
      const blockTime = 15
      let totalTimeSecond = 1000000 * blockTime
      return moment().add(totalTimeSecond, 's')
    }
  },
  methods: {
  },
  mounted () {
  }
}
</script>

<style scoped>
.container {
  max-width: 978px !important;
}
h2 {
  margin-bottom: 1em !important;
  margin-top: 1em !important;
}
h3 {
  margin-bottom: 1em !important;
  margin-top: 1em !important;
}
.card-description {
  margin-top: 0em;
  font-style: italic;
}
.card {
  max-width: 250px !important;
}
.card-image {
  max-height: 100px !important;
}
.ui.cards > .card > .content > .header, .ui.card > .content > .header {
  margin-bottom: 0.1em;
}
.buy-list {
  margin-left: 0.5em;
  color: rgba(0,0,0,.70) !important;
}
.green-hover:hover {
  margin-top: 0.25em;
  margin-bottom: 0.25em;
  background-color: rgba(33, 186, 69, 0.2) ;
}
.red-hover:hover {
  margin-top: 0.25em;
  margin-bottom: 0.25em;
  background-color: rgba(219, 40, 40, 0.2);
}
.orange-hover:hover {
  margin-top: 0.25em;
  margin-bottom: 0.25em;
  background-color: rgba(242, 113, 28, 0.2);
}
</style>
