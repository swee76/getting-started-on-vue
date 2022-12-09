<template>
  <div>
    <input
      type="text"
      placeholder="First Name"
      id="first-name"
      v-model="firstName"
    />
    <input
      type="text"
      placeholder="Last NameI"
      id="last-name"
      v-model="lastName"
    />
  </div>
  <PersonGreeting
    :firstName="firstName"
    :lastName="lastName"
    @callHeroes="callHeroes"
  />
</template>

<script>
import { ref } from "vue";
import PersonGreeting from "./PersonGreeting.vue";
export default {
  name: "PersonVue",
  components: {
    PersonGreeting,
  },
  setup() {
    const firstName = ref("");
    const lastName = ref("");

    function callHeroes(hero) {
      alert(`Calling ${hero}`);
    }
    return {
      firstName,
      lastName,
      callHeroes,
    };
  },
};
</script>

<style></style>
