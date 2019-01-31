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
  }
}
</script>

<style>
body { text-align:center; background-color: #f5f5f5; padding:30px;}

.input-todo { width:100%; font-size:16px; line-height:24px; box-shadow:5px 10px 10px rgba(0,0,0,0.1); border-style:groove; border:0; outline-width:0; padding:10px; }

</style>
