<template>
    <div>
        <drop-up
                :multiselect="multiSelect"
                :options="myOptions"
        ></drop-up>
    </div>
    </template>
    <script>
        import DropUp from "./DropUp";
        export default {
            name: "DropUpContainer",
            data(){
                return{
                    myOptions:[{name:'apples', price:'$2.00'}],
                    multiSelect="true"
                }
            },
            components: {DropUp}
        }
    </script>
