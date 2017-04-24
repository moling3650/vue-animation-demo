<template>
  <div class="demo5">
    <button @click="add">Add</button>
    <button @click="remove">Remove</button>
    <transition-group name="list" tag="p">
      <span v-for="item in items" :key="item" class="list-item">
        {{ item }}
      </span>
    </transition-group>
  </div>
</template>

<script>
  export default {
    name: 'demo5',
    data () {
      return {
        items: [1, 2, 3, 4, 5, 6, 7, 8, 9],
        nextNum: 10
      }
    },
    methods: {
      randomIndex () {
        return Math.floor(Math.random() * this.items.length)
      },
      add () {
        return this.items.splice(this.randomIndex(), 0, this.nextNum++)
      },
      remove () {
        return this.items.splice(this.randomIndex(), 1)
      }
    }
  }
</script>

<style scoped>
  .list-item {
    display: inline-block;
    margin-right: 10px;
  }
  .list-enter-active, .list-leave-active, .list-move {
    transition: all 1s;
  }
  .list-enter, .list-leave-active {
    opacity: 0;
    transform: translateY(-30px);
  }
</style>
