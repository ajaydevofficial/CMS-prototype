<template>
    <b-sidebar
        id="gh-add-elements-sidebar"
        right
        shadow
        body-class="bg-white"
        no-header
    >
        <section class="hl_page-creator--rows-group active">
            <a v-b-toggle:gh-add-elements-sidebar class="close-group" id="close-row-group"><i class="icon icon-close"></i></a>
            <div class="hl_row-group">
            <div class="tab-content" id="hl_row-group-tab">
                <div class="tab-pane fade active show" id="add-row" role="tabpanel" aria-labelledby="add-row-tab">
                    <div class="add-row">
                        <div class="add-row-body">
                            <div class="form-group">
                                <input type="text" class="form-control" placeholder="Search">
                            </div>
                            <p>Text</p>
                            <div class="row-cards">
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-heading fa-w-16"></i>
                                    </div>
                                    <h5>Heading</h5>
                                </div>
                            </div>
                            <p>Media</p>
                            <div class="row-cards">
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-image fa-w-16"></i>
                                    </div>
                                    <h5>Image</h5>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
            </div>
         </section>
    </b-sidebar>
</template>

<script>
import draggable from 'vuedraggable';

export default {
    components: {
        'gh-dragabble': draggable
    },
    data: ()=>{
        return{

        }
    },
    methods:{
        show(){

        },
        hide(){

        }
    }
}
</script>

<style lang="scss" scoped>
    @media (max-width: 767px){
        .hl_page-creator--rows-group {
            top: 0;
        }
    }
</style>