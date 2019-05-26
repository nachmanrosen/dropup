A reusable Vue.js component for a dropup select menu. 

The new version 1.2  uses a DropUpContainer, set the options to be displayed by writing the myOptions data property. The name field is required, but price is optional
There are two states, select: select only one option, multiSelect : select multiple options. For select set multiSelect data property to false, for multiSelect set multiSelect data property to true.
The items selected by the dropup child component are passed by an event to its parent-DropUpContainer and stored in selectedItems.
 
 ```<template>
    <div>
        <drop-up
                :multiselect="multiSelect"
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
                    myOptions:[{name:'apples', price:'$2.00'}],      //write your own options, price is optional
                    multiSelect="true",
                    selectedItems = []
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
