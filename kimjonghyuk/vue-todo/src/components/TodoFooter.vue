<template>
  <div>
    <span class="btn-clear" v-on:click="removeAll">Clear All</span>
  </div>
</template>

<script>
export default {
  methods: {
    removeAll: function(){
      localStorage.clear();
    },
  }
}
</script>

<style>

</style>
