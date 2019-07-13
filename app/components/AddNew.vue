<template>
  <!-- Positions an input field, a button, and the list of tasks in a vertical stack. -->
  <StackLayout orientation="vertical" width="100%" height="100%">
    <!-- Configures the text field and ensures that pressing Return on the keyboard produces the same result as tapping the button. -->
    <TextField
      v-model="location"
      hint="Where are you?"
      editable="true"
      @returnPress="addNewWifiPassword"
    />
    <TextField
      v-model="wifiPassword"
      hint="Whats the wifi password?"
      editable="true"
      @returnPress="addNewWifiPassword"
    />
    <Button text="Add Wifi Password" @tap="addNewWifiPassword" />
    <ListView
      class="list-group"
      for="wifiPasswordItem in wifiPasswordsArray"
      @itemTap="onItemTap"
      style="height:75%"
    >
      <v-template>
        <GridLayout columns="*, *" rows="15, 15">
          <Label
            :text="'Location: ' + wifiPasswordItem.location"
            row="0"
            col="0"
            class="list-group-item-heading"
            backgroundColor="#ECEEF0"
            textWrap="true"
          />
          <Label
            :text="'Password: ' + wifiPasswordItem.wifiPassword"
            row="0"
            col="1"
            class="list-group-item-heading"
            backgroundColor="#ECEEF0"
            textWrap="true"
          />
        </GridLayout>
      </v-template>
    </ListView>
  </StackLayout>
</template>


<script>
const textViewModule = require("tns-core-modules/ui/text-view");
export default {
  data: function() {
    return {
      location: "",
      wifiPassword: "",
      wifiPasswordsArray: [
        {
          location: "Ssss",
          wifiPassword: "jhbodfjh"
        },
        {
          location: "Ssss",
          wifiPassword: "sdfmsdlf"
        },
        {
          location: "Ssss",
          wifiPassword: "jhbmcksjsojh"
        }
      ]
      //   wifiPasswordsArray: this.$store.state.wifiPasswords
    };
  },
  name: "AddNewWifiPassword",
  methods: {
    onItemTap: function(args) {
      console.log("Item with index: " + args.index + " tapped");
    },
    addNewWifiPassword: function() {
      if (!this.location || !this.wifiPassword) {
        alert("Wifi password or location empty");
        return;
      }

      this.wifiPasswordsArray.unshift({
        location: this.location,
        wifiPassword: this.wifiPassword
      });
      console.log("HEREE", JSON.stringify(this.wifiPasswordsArray));
      this.location = "";
      this.wifiPassword = "";
    }
  }
};
</script>
