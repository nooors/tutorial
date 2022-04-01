<template>
  <b-container class="container landing">
    <h1 class="text-center mt-5">Welcome to the Tutorial</h1>
    <p class="text-center py-5">
      Podeu navegar per les passes (episodis en aquest cas) mitjançant els
      botons de navegació de la part superior de la pantalla
    </p>
    <b-button @click="start">Començar</b-button>
  </b-container>
</template>

<script>
export default {
  name: "TheLanding",
  data() {
    return {
      startFlag: false,
    };
  },
  methods: {
    start() {
      this.startFlag = true;
      this.$emit("toogleLanding", this.startFlag);
    },
  },
};
</script>

<style></style>
