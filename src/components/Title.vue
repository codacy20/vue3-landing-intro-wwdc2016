<template>
  <div>
    <span
      v-for="(val, key) in hell0"
      v-bind:key="key"
      :style="[colors ? { color: newColors[key] } : '']"
      class="text"
    >
      {{ val }}
    </span>
    <span class="text" id="two">I'm Amir!</span>
  </div>
  <div>
    /*
    <!-- <span v-for="(val2, key2) in tempTitle" v-bind:key="key2">
      {{ val2 }}
    </span> -->
    <span>{{ tempTitle }}</span>
    */
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
      console.log(counter, self.tempTitle);
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
</style>
