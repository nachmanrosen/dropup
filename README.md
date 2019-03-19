A reusable Vue.js component for a dropup select menu. 
The component takes two props: options: the options to pass into your dropup, each option must contain a name field. buttonText: the text of your dropup button-clicking the button clears your selection.
The component listens to two events, selected and clear.

for example to create a dropup for selecting a specific user or clicking on All Users to clear your selection.   
```<template>
      <drop-up
      :options="myUsers"
      buttonText="All Users"
      @selected="selectUser"
      @clear="clear"
      ></drop-up>
</template>
<script>
      //
    data() {
        return {
            options: [{id:1,name:'Bob'},{id:2,name:Joe}],
        };
    },
      
    methods: {
      selectUser(user) {
            //code
        },
       clear() {
            //code
        },
     },```
