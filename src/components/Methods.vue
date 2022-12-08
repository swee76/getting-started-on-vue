<template>
  <h2>{{ 2 + 3 + 5 }}</h2>
  <h2>{{ 5 + 13 + 5 }}</h2>
  <h2>Add method - {{ add(2, 3, 5) }}</h2>
  <h2>Add method - {{ add(12, 10, 15) }}</h2>
  <h3>Greeting - {{ greeting("john") }}</h3>
  <h2>Multiply method - {{ multiply(10) }}</h2>
  <h3>Multiply method(basevalue) - {{multiply(baseValue)}} </h3>
</template>

<script>
export default {
  name: "MethodsInVue",
  data() {
    return {
      baseMultiplier: 5,
      baseValue: 2,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    greeting(name) {
      return "Hello " + name + "!";
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
  },
};
</script>

<style></style>
