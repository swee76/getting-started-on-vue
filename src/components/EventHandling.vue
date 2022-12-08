<template>
  <h2>{{ name }}</h2>
  <div>
    <h2>Inline logic</h2>
    <button v-on:click="name = 'Batman'">Change name</button>
    <h2>Using methods</h2>
    <button v-on:click="changeName($event), increment(1, $event)">
      Change name using method
    </button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <h2>Inline logic</h2>
    <button v-on:click="count += 1">Increment</button>
    <button v-on:click="count -= 1">Decrement</button>
    <h2>Replace v-on: with @ sign</h2>
    <button @click="count += 1">Increment</button>
    <button @click="count -= 1">Decrement</button>
  </div>
  <div>
    <h2>Using methods</h2>
    <button v-on:click="increment(1, $event)">Increment by 1</button>
    <button v-on:click="decrement(1)">Decrement by 1</button>
    <button v-on:click="increment(5)">Increment by 5</button>
    <button v-on:click="decrement(2)">Decrement by 2</button>
  </div>
</template>

<script>
export default {
  name: "EventHandling",
  data() {
    return {
      name: "Vishwas",
      count: 0,
    };
  },
  methods: {
    changeName() {
      this.name = "Batman";
    },
    increment(num, event) {
      this.count = this.count + num;
      console.log("Event", event);
    },
    decrement(num) {
      this.count = this.count - num;
    },
  },
};
</script>

<style></style>
