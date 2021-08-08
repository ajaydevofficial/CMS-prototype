<template>
  <section class="hl_wrapper nav-shrink d-flex padding-less">
    <section class="hl_wrapper--inner page-creator" id="page-creator">
      <section class="hl_page-creator--main">
        <gh-toolbar :key="toolbarKey"></gh-toolbar>
        <div class="hl_page-creator--content">
          <gh-draggable 
          v-if="mainRows.length>0"
          class="d-contents w-100" 
          v-model="mainRows" 
          group="mainRows"
          @start="drag=true" 
          @end="drag=false"
          handle=".move-actions"
          >
            <gh-row-container :id="row.id" :add="addMainRow" :remove="removeMainRow" v-for="row in mainRows" v-bind:key="row.id"></gh-row-container>
          </gh-draggable>
          <section v-else class="hl_page-creator--section">
            <div href="#" class="new-row-blank">
                <span @click="addMainRow()" class="btn btn-light5 btn-slim">Add row</span>
            </div>
          </section>
        </div>
      </section>
    </section>
  </section>
</template>

<script>
import ghRowContainerVue from '../../components/gh-row-container.vue'
import ghToolbarVue from '../../components/gh-toolbar.vue'

export default {
  components: {
    'gh-toolbar': ghToolbarVue,
    'gh-row-container': ghRowContainerVue
  },
  data: ()=>{
    return{
      recentId: 1,
      mainRows: [
        { id: 1 }
      ],
      toolbarKey: 1
    }
  },
  methods: {
    addMainRow(){
      this.mainRows.push(
        { id: this.recentId + 1}
      )
      this.recentId++;
    },
    removeMainRow(id){
      var index = this.mainRows.findIndex(el=>el.id==id);
      if(index>-1){
        this.mainRows.splice(index,1);
      }else{
        console.error("row does not exist")
      }
      if(this.mainRows.length==0){
        this.recentId = 0;
      }
    },
    remount(){
      this.toolbarKey++;
    }
  }
}
</script>

<style lang="scss" scoped>
    @media (min-width: 767px){
        .hl_page-creator--main{
        margin-top: 85px
      }
    }
</style>