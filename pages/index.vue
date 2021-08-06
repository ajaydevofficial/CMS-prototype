<template>
  <div class="expand-to-viewport">
    <gh-sidebar></gh-sidebar>
  </div>
</template>

<script>
import ghSidebarVue from '../components/gh-sidebar.vue';

export default {
  components:{
    'gh-sidebar': ghSidebarVue
  }
}
</script>

<style scoped lang="scss">
  .expand-to-viewport{
    height: 100vh;
  }
</style>