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
                    @mouseover="col.showControls=true;"
                    @mouseout="col.showControls=false;"
                    v-bind:class="{'border': col.showControls }"
                    >
                        <div class="hl_page-creator--element">
                            <div class="hl_page-creator--actions" v-bind:class="{'opacity-full': col.showControls }">
                                <div class="more-actions">
                                    <span class="move-actions" data-tooltip="tooltip" data-placement="top" title="Move"><i class="fas fa-arrows-alt"></i></span>
                                    <span @click="emptyColumn(col.id)" data-tooltip="tooltip" data-placement="top" title="Move"><i class="fas fa-eraser"></i></span>
                                    <span @click="removeColumn(col.id)" data-tooltip="tooltip" data-placement="top" title="Delete"><i class="far fa-trash-alt"></i></span>
                                </div>
                            </div>
                            <div class="element-container">
                                <gh-element-container :element="col"></gh-element-container>
                            </div>
                        </div>
                    </div>
                </div>
            </gh-draggable>
        </div>
  </div>
</template>

<script>
import ghElementContainerVue from './gh-element-container.vue';

export default {
    props:['columnProperties'],
    components: {
        'gh-element-container': ghElementContainerVue
    },
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
        },
        removeColumn(id){
            var index = this.columnProperties[0].columns.findIndex(el=>el.id==id);
            if(index>-1){
                this.columnProperties[0].columns.splice(index,1)
            }else{
                console.error("Column does not exist")
            }
        },
        emptyColumn(id){
            var index = this.columnProperties[0].columns.findIndex(el=>el.id==id);
            if(index>-1){
                this.columnProperties[0].columns[index].items = [];
                console.log(this.columnProperties[0].columns[index])
            }else{
                console.error("Column does not exist")
            }
        }
    }
}
</script>

<style>

</style>