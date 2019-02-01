<template>
  <div>
    <ul class="list-todo">
      <li v-for="(item, index) in todoItems">
        {{ item }}
        <i class="far fa-trash-alt" v-on:click="removeTodo(item, index)"></i>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data: function(){
    return {
      todoItems: []
    }
  },
  methods: {
    removeTodo: function(item, index){
      localStorage.removeItem(item);
      this.todoItems.splice(index, 1)
    },
  },
  created: function(){
    if(localStorage.length > 0){
      for(var i=0; i < localStorage.length; i++){
        if(localStorage.key(i) !== "loglevel:webpack-dev-server"){
          this.todoItems.push(localStorage.key(i));
        }
      }
    }
  }
}
</script>

<style>

</style>
