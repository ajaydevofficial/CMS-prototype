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
        <div href="#" class="new-row-blank">
            <span class=""><i class="fas fa-arrows-alt mr-2"></i><span>Drag and drop a column</span></span>
        </div>
    </section>
</template>

<script>
export default {
    props:['id', 'add', 'remove'],
    components: {

    },
    data: ()=>{
        return{
            showControls: false
        }
    },
    methods: {

    }
}
</script>

<style lang="scss" scoped>
    .hl_page-creator--section {
        cursor: -webkit-grabbing; 
        cursor: grabbing;
    }
    .opacity-full{
        opacity:1 !important;
    }
</style>