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
                            
                            <div v-for="(category,index) in elementCategories" v-bind:key="index">
                                <p>{{category.title}}</p>
                                <gh-draggable 
                                class="row-cards" 
                                v-model="category.elements" 
                                :group="{ name: 'elements', pull: 'clone', put: false }"
                                @start="drag=true" 
                                @end="drag=false"
                                :clone="cloneElement"
                                >
                                    <div class="row-card" v-for="element in category.elements" v-bind:key="element.id">
                                        <div class="icon">
                                            <i :class="`${element.iconClass} fa-w-16`"></i>
                                        </div>
                                        <h5>{{element.title}}</h5>
                                    </div>
                                </gh-draggable>
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
import cryptoRandomString from 'crypto-random-string';

export default {
    components: {
        'gh-dragabble': draggable
    },
    data: ()=>{
        return{
            elementCategories: [
                {   
                    id: "text",
                    title: "Text", 
                    elements:[
                        { type:"heading", title: "Heading" , iconClass: "fa fa-heading", placeholder: "Heading Text Goes Here" ,value: null}
                    ] 
                },
                { 
                    id: "media",
                    title: "Media", 
                    elements:[
                        { type:"image", title: "Image", iconClass: "fa fa-image", url: null}
                    ] 
                }
            ]
        }
    },
    methods:{
        cloneElement(element){
            var payload = Object.assign(element);
            payload.id = cryptoRandomString({length: 10});
            return payload;
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