<template>
  <input class="input-todo" v-on:click="addTodo" type="text">
</template>

<script>
export default {
  methods : {
    addTodo(){
      console.log('aaa')
    },
  }
}
</script>

<style>

</style>
