<template>
  <div>{{ greet }} {{ name }}</div>
  <div>{{ channel }}</div>
  <div v-text="channel"></div>
  <div v-html="channel"></div>
  <div v-html="hack"></div>
  <h2 :id="headingId">Heading</h2>
  <button :disabled="isDisabled">Bind</button>
  <h2 class="underline">Underlined Text</h2>
  <h2 class="underline" :class="status">Status</h2>
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldOut ? 'sold-out' : 'new'">Soldout? movie</h2>
  <h2 :class="['new', 'promoted']">Newly Promoted Movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">
    Array Conditional Movie
  </h2>
  <h2
    :class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut,
    }"
  >
    Object Conditional Movie
  </h2>
  <!-- fontSize : headerSize + 'px'  is also works -->

  <h2
    :style="{
      color: highlightColor,
      'font-size': headerSize + 'px',
      padding: '20px',
    }"
  >
    Inline Style
  </h2>
  <h2 :style="headerStyleObject">Style Object</h2>
  <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>
  <conditional-rendering />
  <list-rendering />
  <list-and-keys />
  <conditional-list-rendering />
</template>

<script>
import ConditionalListRendering from "./components/ConditionalListRendering.vue";
import ConditionalRendering from "./components/ConditionalRendering.vue";
import ListAndKeys from "./components/ListAndKeys.vue";
import ListRendering from "./components/ListRendering.vue";
export default {
  components: {
    "conditional-rendering": ConditionalRendering,
    "list-rendering": ListRendering,
    "list-and-keys": ListAndKeys,
    "conditional-list-rendering": ConditionalListRendering,
  },
  name: "App",
  data() {
    return {
      greet: "Hello",
      name: "Vishwas",
      channel: "<b>Code Academy</b>",
      hack: `<a href="#" onClick="alert('You have been hacked!')">Win a price!</a>`,
      headingId: "heading",
      isDisabled: false,
      status: "danger",
      isPromoted: true,
      isSoldOut: true,
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: "blue",
        fontSize: "50px",
        padding: "10px",
      },
      baseStyleObject: {
        fontSize: "50px",
        padding: "10px",
      },
      successStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
        padding: "20px",
      },
      dangerStyleObject: {
        color: "darkred",
        backgroundColor: "red",
        border: "1px solid darkred",
      },
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
  text-decoration: underline;
}
.promoted {
  font-style: italic;
}
.sold-out {
  color: red;
}
.new {
  color: green;
}
</style>
