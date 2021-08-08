<template>
    <b-modal
    ref="modal" 
    id="modal"
    no-close-on-backdrop
    hide-header
    hide-footer
    centered
    >
        <template>
            <h4>Media editor</h4>
            <div class="add-row mt-3">
                <div class="add-row-body">
                    <p>Media url</p>
                    <input type="url" v-model="url" class="form-control"/>
                    <button @click="submit(url);clear();hide();" class="btn btn-success mt-3">Submit</button>
                </div>
            </div>
        </template>
    </b-modal>
</template>
<script>

export default {
    props: ['submit'],
    components: {
       
    },
    data: ()=>{
        return{
            url: '',
        }
    },
    methods:{
        show(){
            this.$refs.modal.show();
        },
        hide(){
            this.$refs.modal.hide();
        },
        clear(){
            this.url = '';
        }
    }
}
</script>

<style lang="scss" scoped>
    .hl_page-creator--rows-group .row-cards .row-card:hover {
        background-color: #f2f7fa;
        border-color: #e0ecf3;
        transform: none;
    }
    @media (max-width: 767px){
        .hl_page-creator--rows-group {
            top: 0;
        }
    }
</style>