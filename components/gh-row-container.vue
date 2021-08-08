<template>
    <section :class="showControls?'hl_page-creator--section border': 'hl_page-creator--section'"
    @mouseover="showControls=true"
    @mouseout="showControls=false"
    >
        <div :class="showControls?'hl_page-creator--actions opacity-full':'hl_page-creator--actions'">
            <div class="move-actions">
                <span data-tooltip="tooltip" data-placement="right" title="Down"><i class="fas fa-arrows-alt"></i></span>
            </div>
            <div class="more-actions">
                <span @click="remove(id)" data-tooltip="tooltip" data-placement="left" title="Delete"><i class="far fa-trash-alt"></i></span>
            </div>
        </div>
        <span @click="add()" :class="showControls?'add-new-section opacity-full':'add-new-section'" data-tooltip="tooltip" data-placement="bottom" title="Add New Section"><i class="icon icon-plus"></i></span>
        <gh-draggable 
        class="d-contents w-100 hl_page-creator--section" 
        v-model="columns" 
        group="rows"
        @start="drag=true" 
        @end="drag=false"
        >
            <div v-if="columns.length>0">
                <div v-for="column in columns" :key="column.colNum" :id="`gh-${column.colNum}-column`" class="row-card">
                    <gh-col-container :columnProperties="columns"></gh-col-container>
                </div>
            </div>
            <div v-else href="#" class="new-row-blank">
                <span class=""><i class="fas fa-arrows-alt mr-2"></i><span>Drag and drop a column</span></span>
            </div>
        </gh-draggable>
        
    </section>
</template>

<script>
import ghColContainerVue from './gh-col-container.vue';

export default {
    props:['id', 'add', 'remove'],
    components: {
        'gh-col-container': ghColContainerVue
    }, watch: {
        columns: function (newVal, oldVal) {
            if(this.columns.length>1){
                this.columns = newVal.filter(x => !oldVal.includes(x));
            }
        } 
    },
    data: ()=>{
        return{
            showControls: false,
            columns: []
        }
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
    
</style>