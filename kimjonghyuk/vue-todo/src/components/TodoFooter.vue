<template>
  <div>
    <span class="btn-clear" v-on:click="removeAll">Clear All</span>
  </div>
</template>

<script>
export default {
  methods: {
    removeAll: function(){
      this.$emit('clearAll')
    },
  }
}
</script>

<style>

</style>
