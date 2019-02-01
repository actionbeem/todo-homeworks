<template>
  <div id="app-container">
    <TodoHeader></TodoHeader>
    <TodoInput></TodoInput>
    <TodoList></TodoList>
    <TodoFooter></TodoFooter>
  </div>
</template>

<script>
import TodoHeader from './components/TodoHeader.vue';
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';
import TodoFooter from './components/TodoFooter.vue';

export default {
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
.list-todo li i { position:absolute; top:17px; right:17px; cursor:pointer;}
.fa-trash-alt { color:rgb(65, 159, 221);; }

</style>
