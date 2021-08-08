<template>
    <div>
        <gh-draggable 
        class="row-cards hl_page-creator--row" 
        v-model="element.items" 
        group="elements"
        @start="drag=true" 
        @end="drag=false;$forceUpdate();"
        >
            <div v-if="element.items.length>0" class="w-100">
                <div class="row-card" v-for="item in element.items" v-bind:key="item.id">
                    <!--Add handler for all elements here-->
                    <div v-if="item.type=='image'">
                        <!--if the image url exist show the image else show the button for adding image url-->
                        <gh-add-image-popup ref="imagePopupModal" :submit="submitImageUrl"></gh-add-image-popup>
                        <div v-if="item.url">
                            <img :src="item.url" class="w-100">
                        </div>
                        <div v-else class="hl_page-creator--section w-100">
                            <div @click="showMediaModal()" class="new-row-blank text-center">
                                <span class=""><i class="fas fa-image mr-2"></i><span>Click here to add image</span></span>
                            </div>
                        </div>
                    </div>
                    <div v-if="item.type=='heading'">
                        <h3 class="outline-none font-weight-bold" contenteditable @input="onInput">{{item.value?item.value:item.placeholder}}</h3>
                    </div>
                </div>
            </div>
            <div v-else class="new-element-blank">
                <span class=""><i class="fas fa-arrows-alt mr-2"></i><span>Drag and drop an elemnt</span></span>
            </div>
        </gh-draggable>
    </div>
</template>

<script>

import ghAddImagePopupVue from './gh-add-image-popup.vue';

export default {
    props: ['element'],
    components:{
        'gh-add-image-popup': ghAddImagePopupVue
    },
    watch: {
        "element.items": function (newVal, oldVal) {
            alert()
            if(this.element.items.length>1){
                this.element.items = newVal.filter(x => !oldVal.includes(x));
            }
        } 
    },
    data: ()=>{
        return{

        } 
    },
    methods: {
        onInput(e){
            var text = e.target.innerText;
            if(this.element.items[0].type=='text'){
                this.element.items[0].value = text
            }
            else{
                console.error("Invalid type")
            }
        },
        submitImageUrl(url){
            if(this.element.items[0].type=='image'){
                this.element.items[0].url = url
            }
            else{
                console.error("Invalid type")
            }
        },
        showMediaModal(){
            this.$refs.imagePopupModal[0].show();
        }
    }
}
</script>

<style lang="scss" scoped>
    .outline-none{
        outline: none !important;
    }
</style>    