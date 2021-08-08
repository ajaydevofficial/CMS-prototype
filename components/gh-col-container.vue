<template>
  <div>
        <div class="hl_page-creator--content">
            <gh-draggable 
            :class="`row ${columnProperties[0].bClass}`"
            v-model="columnProperties[0].columns" 
            group="columnProperties"
            @start="drag=true" 
            @end="drag=false;hideAllControls();"
            handle=".move-actions"
            >
                <div class="col" v-for="(col,index) in columnProperties[0].columns" v-bind:key="index">
                    <div 
                    class="hl_page-creator--column"
                    @mouseover="col.showControls=true"
                    @mouseout="col.showControls=false"
                    v-bind:class="{'border': col.showControls }"
                    >
                        <div class="hl_page-creator--element">
                            <div class="hl_page-creator--actions" v-bind:class="{'opacity-full': col.showControls }">
                                <div class="more-actions">
                                <span class="move-actions" data-tooltip="tooltip" data-placement="top" title="Move"><i class="fas fa-arrows-alt"></i></span>
                                <span data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                                </div>
                            </div>
                        <div class="element-container">
                            <h1>Column {{col.id}}</h1>
                        </div>
                        </div>
                    </div>
                </div>
            </gh-draggable>
        </div>
  </div>
</template>

<script>
export default {
    props:['columnProperties'],
    data: ()=>{
        return{
            
        }
    },
    methods: {
        setControlsFalse(column){
            column.showControls = false;
            return column
        },
        hideAllControls(){
            this.columnProperties[0].columns.map(this.setControlsFalse);
        }
    }
}
</script>

<style>

</style>