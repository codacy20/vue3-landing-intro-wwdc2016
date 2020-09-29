<template>
  <Title msg="Hello Vue 3 in CodeSandbox!" :hell0="hell0" :colors="colors" />
</template>

<script>
import Title from "./components/Title.vue";

export default {
  name: "App",
  components: {
    Title,
  },
  setup() {
    const hell0 = "Hello";
    const colors = ["97C774"];
    return {
      hell0,
      colors,
    };
  },
};
</script>

<style>
#app {
  background: #292B36;
  height: 99vh;
  display: flex;
  justify-content: center;
  align-items: center;
  /* width: 100vw; */
}
</style>
