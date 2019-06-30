<template>
    <div>
        <drop-up
                :multiSelect="multiSelect"
                :options="myOptions"
                @select = "select"
        ></drop-up>
    </div>
    </template>
    <script>
        import DropUp from "./DropUp";
        export default {
            name: "DropUpContainer",
            data(){
                return{
                    myOptions:[{name:'apples', price:'$2.00'},{name:'oranges', price :'$2.75'}],
                    multiSelect: "true",
                    selectedItems:[]
                }
            },
            methods:{
                select(selected){
                    this.selectedItems = selected;
                }
            },
            components: {DropUp}
        }
    </script>
