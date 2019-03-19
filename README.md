A reusable Vue.js component for a dropup select menu. 
The component takes two props: options - the options to pass into your dropup, buttonText: the text of your dropup button-
onclick of button clears your selection.
The component listens to two events, selected and clear

for example to create a dropup for selecting All users or a specific user
      <drop-up
      :options="myUsers"
      buttonText="All Users"
      @selected="selectUser"
      @clear="clear"
      ></drop-up>
      
      methods: {
      selectUser(user) {
            //code
        },
        clear() {
            //code
        },
