<template>
  <div id="app">
      <home-tutorial></home-tutorial>
  </div>
</template>

<script>
import homeTutorial from "./components/Home.vue";

export default {
  name: "App",
  components: {
    homeTutorial,
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
}

.message {
  border: 2px solid black;
  border-radius: 1.5rem;
}
.button.col{
  padding: 0
}

.btn-light{
  border-color: black !important;
  font-size: 2rem !important;
}

</style>
