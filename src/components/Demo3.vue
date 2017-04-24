<template>
  <div class="demo3">
    <button @click="show = !show">Toggle</button>
    <transition name="bounce">
      <p v-if="show">hello world</p>
    </transition>
  </div>
</template>

<script>
  export default {
    name: 'demo3',
    data () {
      return {
        show: false
      }
    }
  }
</script>

<style scoped>
  .bounce-enter-active {
    animation: bounce-in .5s;
  }
  .bounce-leave-active {
    animation: bounce-out .5s;
  }

  @keyframes bounce-in {
    0% {
      transform: scale(0);
    }
    50% {
      transform: scale(2);
    }
    100% {
      transform: scale(1);
    }
  }

  @keyframes bounce-out {
    0% {
      transform: scale(1);
    }
    50% {
      transform: scale(2);
    }
    100% {
      transform: scale(0);
    }
  }
</style>
