<template>
  <template v-for="name in names" key="name">
    <h2 v-bind:key="name" v-if="name === 'Bruce'">{{ name }}</h2></template
  >
</template>

<script>
export default {
  name: "ConditionalListRendering",
  data() {
    return {
      names: ["Bruce", "Clark", "Diana"],
    };
  },
};
</script>

<style></style>
