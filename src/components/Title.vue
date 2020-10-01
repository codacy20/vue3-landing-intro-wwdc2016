<template>
  <div class="title-container">
    <div>
      <span
        v-for="(val, key) in hell0"
        v-bind:key="key"
        :style="[colors ? { color: newColors[key] } : '']"
        class="text"
      >
        {{ val }}
      </span>
      <span class="text blinker" id="two">I'm Amir!</span>
    </div>
    <span class="green">
      /*
      <span class="green">{{ tempTitle }}</span>
      */
    </span>
  </div>
</template>

<script>
export default {
  name: "Title",
  props: {
    msg: String,
    hell0: String,
    colors: Array,
    titles: Array,
  },
  data(props) {
    const newColors = props.colors.map((item) => {
      return `#` + item;
    });
    let tempTitle = this.$props.titles[0];
    return {
      newColors,
      tempTitle,
    };
  },
  created: function (props) {
    let counter = 1;
    var self = this;
    setInterval(() => {
      if (counter < this.$props.titles.length - 1) {
        counter = counter + 1;
      } else {
        counter = 0;
      }
      self.tempTitle = this.$props.titles[counter];
    }, 2000);
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.text {
  font-family: "Droid Sans Mono", monospace;
  font-size: 3vw;
}
#two {
  color: white;
}
.title-container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.title-container .green {
  color: #59B75C;
  margin-top: 10%;
  font-size: 2vw;
  font-family: "Droid Sans Mono", monospace;
}
.blinker:after {
  content: "";
  height: 3vw;
  width: 1px;
  background: transparent;
  position: absolute;
  animation: blink 1.2s linear infinite;
}
@keyframes blink {
  49% {
    background: transparent;
  }
  50% {
    background: white;
  }
  100% {
    background: white;
  }
}
</style>
