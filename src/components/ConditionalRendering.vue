<template>
  <h1>Conditional Rendering</h1>
  <h2>v-if, v-else, v-else-if, v-show</h2>
  <h3 v-if="num === 0">The number is zero</h3>
  <h3 v-else-if="num < 0">The number is negative</h3>
  <h3 v-else-if="num > 0">The number is positive</h3>
  <h3 v-else>Not a number</h3>
  <template v-if="display">
    <h2>Vue</h2>
    <h2>is</h2>
    <h2>Javascript</h2>
    <h2>Framework</h2>
  </template>
  <h3 v-show="showElement">using v-show</h3>
  <h3 v-if="showElement">using v-if</h3> 
</template>

<script>
export default {
  name: "ConditionalRendering",
  data() {
    return {
      num: 0,
      display: true,
      showElement: true,
    };
  },
};
</script>

<style></style>
