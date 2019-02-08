<template>
  <div>
    <ul class="list-todo">
      <li v-for="(todoItem , index) in propsdata" v-bind:key="todoItem.item">
        <i class="fas fa-check" v-bind:class="{completed: todoItem.completed}" v-on:click="toggleComplete(todoItem, index)"></i>
        <span v-bind:class="{textCompleted: todoItem.completed}">{{ todoItem.item }}</span>
        <i class="far fa-trash-alt" v-on:click="removeTodo(todoItem, index)"></i>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['propsdata'],
  methods: {
    removeTodo: function(todoItem, index){
      this.$emit('removeItem', todoItem, index)
    },
    toggleComplete: function(todoItem, index){
      this.$emit('toggleItem', todoItem, index)
    },
  },

}
</script>

<style>

</style>
