A reusable Vue.js component for a dropup select menu. 

The new version 1.2  uses a DropUpContainer, set the options to be displayed by writing the myOptions data property. The name field is required, but price is optional
There are two states, select: select only one option, multiSelect : select multiple options. For select set multiSelect data property to false, for multiSelect set multiSelect data property to true.
 
 
 ```<template>
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
                    myOptions:[{name:'apples', price:'$2.00'}],      //write your own options, 
                    multiSelect="true"
                }
            },
            components: {DropUp}
        }
    </script>```
