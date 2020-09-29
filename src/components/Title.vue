<template>
  <span v-for="(val, key) in hell0" v-bind:key="key" style="color: colors[0]">
    {{ val }}
  </span>
</template>

<script>
export default {
  name: "Title",
  props: {
    msg: String,
    hell0: String,
    colors: Array,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
