<template>
  <div class="hello">
    <h1>Jack Nolan</h1>
    <h2>Jack's Cool test page - wowzers</h2>
    <button v-on:click="todoButton">todo button: {{ counter }}</button>
    <p v-if="showTodoTitle">{{ todoTitle }}</p>
  </div>
</template>

<script>
import { mapActions, mapState } from 'vuex'

export default {
  name: 'HelloWorld',
  data () {
    return {
      counter: 0
    }
  },
  computed: {
    ...mapState(['todoTitle']),
    showTodoTitle: function () {
      return this.todoTitle && this.todoTitle !== ''
    }
  },
  methods: {
    ...mapActions(['getTodoTitle']),
    todoButton: function () {
      this.getTodoTitle(this.counter)
      this.counter++
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
</style>
