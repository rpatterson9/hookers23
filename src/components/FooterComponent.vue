<template>
  <footer class="ui four item stackable menu">
    <a target="_blank" href="https://etherscan.io/" class="item item-1">
      <i class="fa fa-file"></i>
      Contract
    </a>
    <router-link :to="{ name: 'FAQ'}"  class="item item-2">
      <i class="fa fa-question"></i>
      FAQ
    </router-link>
    <a href="https://pornhub.com" class="item item-3">
      Discord
    </a>
    <a target="_blank" href="https://metamorphos.is" class="item item-4">
      <i class="fa fa-terminal "></i>
      metamorphosis
    </a>
  </footer>
</template>

<script>

export default {
  name: 'footerComponent',
  computed: {
  },
  methods: {
  }
}
</script>

<style scoped>
.menu {
  border-radius: 0em !important;
}
.item {
  border-radius: 0em !important;
  color: rgba(255, 255 ,255, 0.98)!important;
  color: rgba(255, 107, 74, 1) !important;
}
.item:hover {
  color: rgba(255, 255 ,255, 0.98) !important;
}
.item-1:hover {
  background-color: rgba(255, 107, 74, 1) !important;
}
.item-2:hover {
  background-color: #F8C75B !important;
}
.item-3:hover {
  background-color: #E3DD84 !important;
}
.item-4:hover {
  background-color: #5DA086 !important;
}
/*
a:hover {
  background-color: rgba(255, 107, 74, 1)!important;
  color: rgba(255, 255 ,255, 0.98) !important;
}
*/
.fa {
  margin-right: 0.25em !important;
}
.fab {
  margin-right: 0.25em !important;
}
</style>
