<template>
  <h2>Volume Tracker (0-20)</h2>
  <h3>Current Volume - {{ volume }}</h3>
  <div>
    <button @click="volume += 2">Increase</button>
    <button @click="volume -= 2">Decrease</button>
  </div>
  <input type="text" v-model="movie" />
  <input type="text" v-model="movieInfo.title" />
  <input type="text" v-model="movieInfo.actor" />
  <div>
    <button @click="movieList.push('Wonder woman')">Add movie</button>
    <!-- comment out the deep property which is in inside the movieList watcher and see -->
    <button @click="movieList = movieList.concat(['Harry Potter'])">
      Add movie without deep property
    </button>
  </div>
</template>

<script>
export default {
  name: "WatchersVue",
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["Batman", "Superman"],
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
    // Watchers only execute when data changes, not in the page loading,
    // To make it execute in page loading, make the data property name as object instead of making it as a function
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`);
      },
      immediate: true,
    },
    // Watchers by default will not waatch for deeply nested properties, so we have to give it deep property
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`
        );
      },
      deep: true,
    },
    movieList: {
      handler(newValue) {
        console.log(`Updated list ${newValue}`);
      },
      deep: true,
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
