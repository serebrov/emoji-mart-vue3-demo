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

  <div class="row">
    <emoji
      :data="emojiIndex"
      :emoji="santaEmojiObject"
      :size="32"
      @click="showEmoji"
    />
  </div>
</template>

<script>
import data from 'emoji-mart-vue-fast/data/all.json'

// Note: component needs to be imported from /src subfolder:
import { Picker, Emoji, EmojiIndex } from 'emoji-mart-vue-fast/src'
// Import version to test locally:
// import { Picker, Emoji, EmojiIndex } from '../../emoji-mart-vue/src'

let emojiIndex = new EmojiIndex(data)

export default {
  name: 'App',
  components: {
    Picker,
    Emoji,
  },

  data() {
    return {
      emojiIndex: emojiIndex,
      emojisOutput: '',
    }
  },

  methods: {
    showEmoji(emoji) {
      this.emojisOutput = this.emojisOutput + emoji.native
    },
  },

  computed: {
    santaEmojiObject() {
      return emojiIndex.findEmoji(':santa:')
    },
  },
}
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
