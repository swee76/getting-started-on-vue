<template>
  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume - {{ volume }}</h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
</template>

<script>
export default {
  name: "WatchersVue",
  data() {
    return {
      volume: 0,
    };
  },
  methods: {},
  //  Use computed properties when :
  //  You need to compose new data from existing data sources
  // You need to reduce the length of a variable (deeply nested variable)
  computed: {},
  // Use watchers when :
  // You have to check if a property has changed to a favourable value to know if you're ready to  perform an action
  // You have to call an API in response to change in application data
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert(
          "Listening to a high volume for a long time may damage your hearing"
        );
      }
    },
  },
};
</script>

<style>
div,
button {
  text-align: center;
}
</style>
