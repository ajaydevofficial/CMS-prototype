<template>
    <div>
        <gh-add-elements-sidebar></gh-add-elements-sidebar>
        <gh-add-columns-sidebar></gh-add-columns-sidebar>
        <div class="hl_page-creator--menu d-flex align-items-center justify-content-space-between">
            <div class="menu--left"></div>
            <div class="menu--right">
                <div class="btn-group">
                    <button v-b-toggle:gh-add-columns-sidebar type="button" class="btn btn-light btn-sm">
                        <i class="fa fa-bars"></i>
                        <span class="btn-text">Rows</span>
                    </button>
                    <button v-b-toggle.gh-add-elements-sidebar type="button" class="btn btn-light btn-sm">
                        <i class="fa fa-code"></i>
                        <span class="btn-text">Elements</span>
                    </button>
                </div>
                <div class="btn-group">
                    <button type="button" class="btn btn-light btn-sm" data-tooltip="tooltip" data-placement="top" title="" data-original-title="Save">
                        <i class="fa fa-save"></i>
                        <span class="btn-text">Save</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import ghAddColumnsSidebarVue from './gh-add-columns-sidebar.vue';
import ghAddElementsSidebarVue from './gh-add-elements-sidebar.vue';

export default {    
    components:{
        'gh-add-elements-sidebar': ghAddElementsSidebarVue,
        'gh-add-columns-sidebar': ghAddColumnsSidebarVue
    },
    data: ()=>{
        return{

        }
    },
    methods:{

    }
}
</script>

<style lang="scss" scoped>

</style>