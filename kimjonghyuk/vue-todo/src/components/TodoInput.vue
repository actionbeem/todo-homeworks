<template>
  <div class="input-wrap">
    <input class="input-todo" v-model="todoItem" type="text" v-on:keyup.enter="addTodo">
    <button v-on:click="addTodo">OK</button>
  </div>
</template>

<script>
export default {
  data: function(){
    return {
      todoItem : ""
    }
  },
  methods: {
    addTodo: function(){
      localStorage.setItem(this.todoItem, this.todoItem)
      this.clearInput();

      console.log()
    },
    clearInput: function(){
      this.todoItem = "";
    },
  }
}
</script>

<style>

</style>
