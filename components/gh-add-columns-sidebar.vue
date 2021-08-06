<template>
    <b-sidebar
        id="gh-add-columns-sidebar"
        right
        shadow
        body-class="bg-white"
        backdrop
        backdrop-variant="dark"
        no-header
    >
        <section class="hl_page-creator--rows-group active">
            <a v-b-toggle:gh-add-columns-sidebar class="close-group" id="close-row-group"><i class="icon icon-close"></i></a>
            <div class="hl_row-group">
            <div class="tab-content" id="hl_row-group-tab">
                <div class="tab-pane fade active show" id="add-row" role="tabpanel" aria-labelledby="add-row-tab">
                    <div class="add-row">
                        <h2>Add Row</h2>
                        <div class="add-row-body">
                            <div class="row-cards">
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>1 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>2 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>3 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>4 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>5 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>6 Column</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>Left Sidebar</h5>
                                </div>
                                <div class="row-card">
                                    <div class="icon">
                                        <i class="fa fa-columns fa-w-16"></i>
                                    </div>
                                    <h5>Right Sidebar</h5>
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
export default {
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