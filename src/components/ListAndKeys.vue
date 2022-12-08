<template>
  <template v-for="name in names" :key="name">
    <h2>{{ name }}</h2>
    <input type="text" placeholder="Last name" />
    <hr />
  </template>
  <button @click="shuffle">Shuffle!</button>
</template>

<script>
import _ from "lodash";
export default {
  name: "ListAndKeys",
  data() {
    return {
      names: ["Bruce", "Clark", "Diana", "Barry"],
    };
  },
  methods: {
    shuffle() {
      console.log(this.names);
      this.names = _.shuffle(this.names);
    },
  },
};
</script>

<style></style>
