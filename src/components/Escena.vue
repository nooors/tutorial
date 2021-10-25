<template>
  <div>
      <p class="message py-2 px-1 mx-3"
      :class="setClass">{{ row.content }}</p>
  </div>
</template>

<script>
export default {
    name: 'escenaTutorial',
    props: {
      isActive: Boolean,
      row: [],
    },
    computed: {
      setClass(){
        return this.isActive ? "active" : "inactive";   
    }
  }
};
</script>

<style>
  .active{
    background-color: hsl(350, 100%, 88%);
  }

  .inactive{
    background-color: hsla(0, 100%, 100%, 70%);
   }
   
</style>