<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!--HelloWorld msg="Welcome to Your Vue.js App"/-->

  <div class="row">
    <StaticPicker :data="emojiIndex" set="twitter" @select="showEmoji" />
  </div>

  <div class="row">{{ emojisOutput }}</div>
</template>

<script>
/* import HelloWorld from './components/HelloWorld.vue' */

/* import data from "emoji-mart-vue-fast/data/all.json"; */
/* import { Picker, EmojiIndex } from "emoji-mart-vue-fast"; */
/* import "emoji-mart-vue-fast/css/emoji-mart.css"; */
import data from "../../emoji-mart-vue/data/all.json";
import { StaticPicker, EmojiIndex } from "../../emoji-mart-vue/src";
import "../../emoji-mart-vue/css/emoji-mart.css";

let emojiIndex = new EmojiIndex(data);

export default {
  name: "App",
  components: {
    /* HelloWorld, */
    StaticPicker
  },

  data() {
    return {
      emojiIndex: emojiIndex,
      emojisOutput: ""
    };
  },

  methods: {
    showEmoji(emoji) {
      this.emojisOutput = this.emojisOutput + emoji.native;
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
