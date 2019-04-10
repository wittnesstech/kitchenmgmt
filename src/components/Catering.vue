<template>
  <v-container>
    <v-flex mb-8>
      <h2 xs-4 md-6 v-on:click="addItem()">Inventory     +</h2>
      <!-- <v-btn color="green" fab small >
        <v-icon>add</v-icon>
      </v-btn> -->
    </v-flex>
    <v-layout row wrap v-for="item in inventory">
      <!-- TODO: click to dit fields  https://stackoverflow.com/questions/45050119/click-to-edit-text-field-with-vue -->
      <v-flex xs2>
        <v-text-field label placeholder="Quantity purchased" v-model="item.qty"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-text-field dark label="x" placeholder="Item Name" v-model="item.name"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-select :items="allUnits" label="in" v-model="item.units"></v-select>
      </v-flex>
      <v-flex xs2>
        <v-text-field bold label="for Rs" placeholder="Billed Cost" v-model="item.cost"></v-text-field>
      </v-flex>
      <v-flex xs2>
        <v-chip>
          <v-avatar color="teal">@</v-avatar>
          {{item.cost/item.qty}} per {{item.units}}
        </v-chip>
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
