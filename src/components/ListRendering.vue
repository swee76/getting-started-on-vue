<template>
  <h2 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h2>
  <h2 v-for="name in fullNames" :key="name.first">
    {{ name.first }} {{ name.last }}
  </h2>
  <div v-for="actor in actors" :key="actor.name">
    <h2>{{ actor.name }}</h2>
    <h3 v-for="movie in actor.movies" :key="movie">{{ movie }}</h3>
  </div>
  <h2 v-for="(value, key, index) in myInfo" :key="value">
    {{ index }} {{ key }} {{ value }}
  </h2>
  <template v-for="name in names" :key="name"
    >{{ name }}
    <hr
  /></template>
</template>

<script>
export default {
  name: "ListRendering",
  data() {
    return {
      lol: "Lol",
      names: ["Bruce", "Clark", "Diana"],
      fullNames: [
        { first: "Bruce", last: "Wayne" },
        { first: "Clark", last: "Kent" },
        { first: "Princess", last: "Diana" },
      ],
      actors: [
        { name: "Christian Bale", movies: ["Batman", "The Prestige"] },
        { name: "Di Caprio", movies: ["Titanic", "Inception"] },
      ],
      myInfo: {
        name: "Vishwas",
        channel: "Code Academy",
        course: "Vue 3",
      },
    };
  },
};
</script>

<style></style>
