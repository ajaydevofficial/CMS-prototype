<template>
  <div class="expand-to-viewport">
    <gh-sidebar></gh-sidebar>
    <div class="sidebar-padding">
      <gh-top-bar></gh-top-bar>
      <nuxt-child></nuxt-child>
    </div>
  </div>
</template>

<script>
import ghSidebarVue from '../components/gh-sidebar.vue';
import ghTopBarVue from '../components/gh-top-bar.vue';

export default {
  components:{
    'gh-sidebar': ghSidebarVue,
    'gh-top-bar': ghTopBarVue
  }
}
</script>

<style scoped lang="scss">
  .expand-to-viewport{
      height: 100vh;
  }
  .sidebar-padding{
      padding-left: 70px
  }
  @media (max-width: 767px){
    .sidebar-padding{
      padding-left: 0px
    }
  }
  
</style>