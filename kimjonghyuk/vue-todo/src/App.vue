<template>
  <div id="app-container">
    <TodoHeader></TodoHeader>
    <TodoInput v-on:addTodoItem="addOneItem"></TodoInput>
    <TodoList v-bind:propsdata="todoItems"></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import TodoFooter from './components/TodoFooter.vue';

export default {
  data: function(){
    return {
      todoItems: []
    }
  },
  methods: {
    addOneItem: function(todoItem){
      var obj = { completed: false, item: todoItem };
      localStorage.setItem(todoItem,  JSON.stringify(obj))
      this.todoItems.push(obj)
    }
  },
  created: function(){   
    if(localStorage.length > 0){
      for(var i=0; i < localStorage.length; i++){
        if(localStorage.key(i) !== "loglevel:webpack-dev-server"){
          // this.todoItems.push(localStorage.key(i));
          // this.todoItems.push(JSON.parse(localStorage.getItem(localStorage.key(i))) );
          var a = JSON.parse(localStorage.getItem(localStorage.key(i)))
          this.todoItems.push(a)
        }
      }
    }
  },
  components: {
    'TodoHeader' : TodoHeader,
    'TodoInput' : TodoInput,
    'TodoList' : TodoList,
    'TodoFooter' : TodoFooter,
  },
}
</script>

<style>
body { text-align:center; background-color: #f5f5f5; padding:30px;}
ol, ul { list-style:none; margin:0; padding:0; }

.input-wrap { position:relative; }
.input-wrap button { position:absolute; top:6px; right:6px; display:inline-block; width:60px; line-height:30px; text-align:center; background-color:#333; color:#fff; border-radius:3px; border:0; outline-width:0; }
.input-todo { width:100%; font-size:16px; line-height:24px; box-shadow:5px 10px 10px rgba(0,0,0,0.1); border-style:groove; border:0; outline-width:0; padding:10px; box-sizing:border-box; }

.list-todo { margin-top:30px;}
.list-todo li { padding:15px; background-color:#fff; margin-bottom:10px; border-radius:3px; text-align:left; position:relative; }
.list-todo li i.fa-trash-alt { position:absolute; top:17px; right:17px; cursor:pointer; color:rgb(65, 159, 221);} 
.list-todo li i.fa-check { color:rgb(65, 207, 160); margin-right:6px; }
.list-todo li i.fa-check.completed { color:#bbb; }

.textCompleted { color:#bbb; text-decoration:line-through; }
.btn-clear { display:inline-block; background-color:#999; color:#fff; width:120px; border-radius:3px; cursor:pointer; padding:13px 0 10px; margin-top:30px;  }

</style>
