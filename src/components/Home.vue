<template>
  <div class="wrapper image" :class="textos[currentSentence].image">
    <b-container fluid>
      <b-row class="py-4">
        <b-col class="button">
          <button-custom @passhere="backflag"
            ><slot>Anterior</slot></button-custom
          >
        </b-col>
        <b-col class="button">
          <button-custom @passhere="fordwardflag"
            ><slot>Següent</slot></button-custom
          >
        </b-col>
      </b-row>
      <escena-tutorial
        v-for="text in textos"
        :key="text.key"
        :isActive="text.isValid"
        :row="text"
      ></escena-tutorial>
    </b-container>
  </div>
</template>

<script>
import escenaTutorial from "./Escena.vue";
import buttonCustom from "./ButtonCustom.vue";

export default {
  name: "homeTutorial",
  components: {
    escenaTutorial,
    buttonCustom,
  },
  data() {
    return {
      textos: [
        {
          content:
            "El nostre heroi estava surant per l'espai sideral quen a la llunyania va albirar una nau espacial",
          isValid: true,
          image: "image1"
        },
        {
          content:
            "Sentia curiositat per l'interior de la nau i es va posar a inspeccionar-la. Va arribar a una sala amb dues portes",
          isValid: false,
          image: "image2"
        },
        {
          content:
            "L'heroi va decidir travessar la porta que el portava a casa",
          isValid: false,
          image: "image3"
        },
        {
          content:
            "Mentrstant, altres heroes no van tinir tanta sort en la seva elecció...",
          isValid: false,
          image: "image4"
        },
      ],
      currentSentence: 0,
    };
  },

  methods: {
    isCurrent() {
      this.currentSentence = true;
    },
    backflag() {
      if (this.currentSentence > 0) {
        this.textos[this.currentSentence].isValid = false;
        this.currentSentence--;
        this.textos[this.currentSentence].isValid = true;
      }
    },
    fordwardflag() {
      if (this.currentSentence < this.textos.length - 1) {
        this.textos[this.currentSentence].isValid = false;
        this.currentSentence++;
        this.textos[this.currentSentence].isValid = true;
      }
    },
  },
};
</script>

<style>
.container-fluid {
  width: 90% !important 
}

.wrapper {
  height: 100vh;
}

.wrapper.image.image1{
  background-image: url('../assets/img/1.jpg');
}

.wrapper.image.image2{
  background-image: url('../assets/img/2.jpg');
}

.wrapper.image.image3{
  background-image: url('../assets/img/3.jpg');
}

.wrapper.image.image4{
  background-image: url('../assets/img/4.jpg');
}

.wrapper.image{
  
  background-repeat: no-repeat;
  background-size: contain;
  background-size: 100%;
  background-position: center;
}
</style>
