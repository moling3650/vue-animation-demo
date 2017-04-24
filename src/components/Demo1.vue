<template>
  <div class="demo1">
    <button @click="show = !show">Toggle</button>
    <transition name="fade">
      <p v-if="show">hello world</p>
    </transition>
  </div>
</template>

<script>
  export default {
    name: 'demo1',
    data () {
      return {
        show: false
      }
    }
  }
</script>

<style scoped>
  .fade-enter-active, .fade-leave-active {
    transition: opacity 1s;
  }

  .fade-enter, .fade-leave-active {
    opacity: 0;
  }
</style>
