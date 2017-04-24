<template>
  <div class="demo2">
    <button @click="show = !show">Toggle</button>
    <transition name="fade">
      <p v-if="show">hello world</p>
    </transition>
  </div>
</template>

<script>
  export default {
    name: 'demo2',
    data () {
      return {
        show: false
      }
    }
  }
</script>

<style scoped>
  .fade-enter-active {
    transition: all .5s ease;
  }

  .fade-leave-active {
    transition: all 1s cubic-bezier(1.0, 0.5, 0.8, 1.0);
  }

  .fade-enter, .fade-leave-active {
    transform: translate3d(100px, -40px, 0);
    opacity: 0;
  }
</style>
