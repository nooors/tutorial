<template>
  <div class="button">
      <b-button block variant="light"
      @click="isPress"
      >
          <slot></slot>
      </b-button>
  </div>
</template>

<script>
export default {
    name: 'buttonCustom',

    methods: {
        isPress(){
            this.$emit('passhere')
        }
    }

}
</script>

<style>
  
</style>