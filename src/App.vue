<template>
  <Title
    msg="Hello Vue 3 in CodeSandbox!"
    :hell0="hell0"
    :colors="colors"
    :titles="titles"
  />
</template>

<script>
import Title from "./components/Title.vue";

export default {
  name: "App",
  components: {
    Title,
  },
  setup() {
    const hell0 = "Hello,";
    const colors = ["97C774", "B63E98", "D18E62", "DB3E41", "1BABA5", "97C774"];
    const titles = [
      "web developer",
      "devops engnieer",
      "freelancer",
      "citizen",
    ];
    return {
      hell0,
      colors,
      titles,
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
}
</style>
