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
    removeTodo: function(item, index){
      localStorage.removeItem(item);
      this.todoItems.splice(index, 1)
    },
    toggleComplete: function(todoItem, index){
      todoItem.completed = !todoItem.completed;
      localStorage.removeItem(todoItem.item)
      localStorage.setItem(todoItem.item, JSON.stringify(todoItem));
    },
  },

}
</script>

<style>

</style>
