<template>
  <section class="hl_wrapper nav-shrink d-flex">
    <section class="hl_wrapper--inner page-creator" id="page-creator">
      <section class="hl_page-creator--main">
        <gh-toolbar></gh-toolbar>
        
      </section>
    </section>
  </section>
</template>

<script>
import ghToolbarVue from '../../components/gh-toolbar.vue'

export default {
  components: {
    'gh-toolbar': ghToolbarVue
  },
  data: ()=>{
    return{

    }
  },
  methods: {

  }
}
</script>

<style>

</style>