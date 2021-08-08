<template>
    <b-sidebar
        id="gh-add-columns-sidebar"
        right
        shadow
        body-class="bg-white"
        no-header
    >
        <section class="hl_page-creator--rows-group active">
            <a v-b-toggle:gh-add-columns-sidebar class="close-group" id="close-row-group"><i class="icon icon-close"></i></a>
            <div class="hl_row-group">
            <div class="tab-content" id="hl_row-group-tab">
                <div class="tab-pane fade active show" id="add-row" role="tabpanel" aria-labelledby="add-row-tab">
                    <div class="add-row">
                        <h2>Add Columns</h2>
                        <div class="add-row-body">
                            <div class="row-cards">
                                <gh-draggable 
                                class="d-contents w-100" 
                                v-model="rows" 
                                :group="{ name: 'rows', pull: 'clone', put: false }"
                                @start="drag=true" 
                                @end="drag=false"
                                >
                                    <div v-for="row in rows" :key="row.colNum" :id="`gh-${row.colNum}-column`" class="row-card">
                                        <div class="icon">
                                            <i class="fa fa-columns fa-w-16"></i>
                                        </div>
                                        <h5>{{row.text}}</h5>
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

import cryptoRandomString from 'crypto-random-string';

export default {
    data: ()=>{
        return{
            rows:[
                { 
                    colNum: 1, 
                    text: "1 Column", 
                    bClass: 'row-cols-1' , 
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ]
                },
                { 
                    colNum: 2, 
                    text: "2 Column", 
                    bClass: 'row-cols-1 row-cols-md-2', 
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}, 
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ] 
                },
                { 
                    colNum: 3, 
                    text: "3 Column", 
                    bClass: 'row-cols-1 row-cols-md-1',
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}, 
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ] 
                },
                { 
                    colNum: 4, 
                    text: "4 Column", 
                    bClass: 'row-cols-1 row-cols-sm-2 row-cols-md-4' ,
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}, 
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ] 
                },
                { 
                    colNum: 5, 
                    text: "5 Column", 
                    bClass: 'row-cols-1 row-cols-md-1',
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}, 
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ] 
                },
                { 
                    colNum: 6, 
                    text: "6 Column", 
                    bClass: 'row-cols-1 row-cols-sm-2 row-cols-md-6',
                    columns: [
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}, 
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []},
                        {id: cryptoRandomString({length: 10}), showControls: false, items: []}
                    ]
                }
            ]
        }
    },
    methods:{
    }
}
</script>

<style lang="scss" scoped>
    .d-contents{
        display: contents;
    }
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