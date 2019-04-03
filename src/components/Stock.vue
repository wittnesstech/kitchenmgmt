<template>
  <v-container>
    <v-layout text-sm-center text-lg-left wrap>
      <v-flex mb-4>
        <h1 class="display-2 font-weight-bold mb-3">Inventory</h1>
      </v-flex>
    </v-layout>
    <!-- layout dimensions??? 
    text-sm-center text-lg-left wrap
    -->

    <!-- layout dimensions??? -->
    <v-btn color="green" fab small v-on:click="addItem()">
      <v-icon>add</v-icon>
    </v-btn>
    <v-layout row wrap v-for="item in inventory">
      <v-flex xs2>
        <v-text-field label placeholder="Quantity purchased" :value="item.qty"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-text-field dark label="x" placeholder="Item Name" :value="item.name"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-select :items="allUnits" label :value="item.unit"></v-select>
        <!-- <v-text-field light label="in" placeholder="Units" :value="item.units"></v-text-field> -->
      </v-flex>
      <v-flex xs2>
        <v-text-field bold label="Rs" placeholder="Billed Cost" :value="item.cost"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-text-field primary label="@" placeholder="Unit Rate" :value="item.cost/item.qty"></v-text-field>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  data: () => ({
    inventory: [
      {
        name: "apples",
        qty: "10",
        units: "Kgs",
        cost: 500
      },
      {
        name: "Eggs",
        qty: "1",
        units: "Nos",
        cost: 50
      },
      {
        name: "aata",
        qty: "1",
        units: "Kgs",
        cost: 100
      }
    ],
    allUnits: ["Nos", "Kgs", "Lits"]
  }),
  methods: {
    addItem: function() {
      // alert("asd");
      console.log("asd");
      this.inventory.push({});
    }
  }
};
</script>

<style></style>
