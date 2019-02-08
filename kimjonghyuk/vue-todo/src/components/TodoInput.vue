<template>
  <div class="input-wrap">
    <input class="input-todo" v-model="newTodoItem" type="text" v-on:keyup.enter="addTodo">
    <button v-on:click="addTodo">OK</button>
  </div>
</template>

<script>
export default {
  data: function(){
    return {
      newTodoItem : ""
    }
  },
  methods: {
    addTodo: function(){
      if(this.newTodoItem !== ''){
        this.$emit('addTodoItem', this.newTodoItem)
        this.clearInput();
      }
    },
    clearInput: function(){
      this.newTodoItem = "";
    },
  }
}
</script>

<style>

</style>
