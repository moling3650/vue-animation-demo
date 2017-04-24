<template>
  <div class="demo6">
    <button @click="shuffle">Shuffle</button>
    <button @click="add">Add</button>
    <button @click="remove">Remove</button>
    <transition-group name="list-complete" tag="p">
      <span v-for="item in items" :key="item" class="list-complete-item">
        {{ item }}
      </span>
    </transition-group>
  </div>
</template>

<script>
  import _ from 'lodash'

  export default {
    name: 'demo6',
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
        this.items.splice(this.randomIndex(), 0, this.nextNum++)
      },
      remove () {
        this.items.splice(this.randomIndex(), 1)
      },
      shuffle () {
        this.items = _.shuffle(this.items)
      }
    }
  }
</script>

<style scoped>
  .list-complete-item {
    display: inline-block;
    margin-right: 10px;
    transition: all 1s;
  }

  .list-complete-enter, .list-complete-leave-active {
    opacity: 0;
    transform: translateY(30px);
  }

  .list-complete-leave-active {
    position: absolute;
  }
</style>
