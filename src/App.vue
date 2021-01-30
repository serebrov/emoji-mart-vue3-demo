<template>
  <div class="row">
    <img alt="Vue logo" src="./assets/logo.png" />
  </div>

  <div class="row">
    <Picker :data="emojiIndex" set="twitter" @select="showEmoji" />
  </div>

  <div class="row">
    <div>
      {{ emojisOutput }}
    </div>
  </div>
</template>

<script>
import data from "emoji-mart-vue-fast/data/all.json";
import { Picker, EmojiIndex } from "emoji-mart-vue-fast/src";
import "emoji-mart-vue-fast/css/emoji-mart.css";

let emojiIndex = new EmojiIndex(data);

export default {
  name: "App",
  components: {
    Picker
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
  color: #2c3e50;
  margin-top: 60px;
}

.row {
  display: flex;
}

.row > * {
  margin: auto;
}
</style>
