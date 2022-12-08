<template>
  <h2>FullName - {{ firstName }} {{ lastName }}</h2>
  <h2>Computed FullName - {{ fullName }}</h2>
  <h2>
    Total - {{ items.reduce((total, curr) => (total = total + curr.price), 0) }}
  </h2>
  <h2>Computed Total - {{ total }}</h2>
  <button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
    Add item
  </button>
  <h2>Method Total - {{ getTotal() }}</h2>
  <input type="text" v-model="country" />
  <template v-for="item in items" :key="item.id"
    ><h2>{{ item.title }} {{ item.price }}</h2>
  </template>
  <h2 v-for="item in expensiveItems" :key="item.id">
    {{ item.title }} {{ item.price }}
  </h2>
</template>

<script>
export default {
  name: "ComputedProperties",
  data() {
    return {
      firstName: "Bruce",
      lastName: "Wayne",
      items: [
        { id: 1, title: "TV", price: 100 },
        { id: 2, title: "Phone", price: 200 },
        { id: 3, title: "Laptop", price: 300 },
      ],
      country: "",
    };
  },
  methods: {
    getTotal() {
      // This method calculates the total again and again when page rerendering
      console.log("getTotal Method");
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
  },
  computed: {
    fullName() {
      return `${this.firstName} ${this.lastName}`;
    },
    total() {
      // This method returns cached total, so when page rendering it doesn't calculate again and again, therefore this method optimises the code
      console.log("total computed property");
      return this.items.reduce(
        (total, curr) => (total = total + curr.price),
        0
      );
    },
    expensiveItems() {
      return this.items.filter((item) => item.price > 100);
    },
  },
};
</script>

<style></style>
