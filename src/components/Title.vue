<template>
  <span
    v-for="(val, key) in hell0"
    v-bind:key="key"
    :style="[colors ? { color: newColors[key] } : '']"
  >
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
  data(props) {
    const newColors = props.colors.map((item) => {
      return `#` + item;
    });
    return {
      newColors,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
span {
  font-family: "Droid Sans Mono", monospace;
  font-size: 3vw;
}
</style>
