<template>
  <button @click="toggle">Toggle Picker</button>
  <Picker
    v-if="emojiPickerSelected"
    :data="emojiIndex"
    title="Pick your emoji…"
    emoji="point_up"
    @select="convertEmoji"
  />
</template>

<script>
import { ref } from 'vue'
import { Picker, EmojiIndex } from 'emoji-mart-vue-fast/src'
import data from 'emoji-mart-vue-fast/data/all.json'

export default {
  name: 'EmojiPicker',
  components: {
    Picker,
  },
  emits: ['updateEmoji'],
  setup(props, context) {
    const emojiPickerSelected = ref(false)
    let emojiIndex = new EmojiIndex(data)

    const toggle = () => {
      emojiPickerSelected.value = !emojiPickerSelected.value
    }

    const convertEmoji = (emoji) => {
      context.emit('updateEmoji', emoji.native)
    }

    return {
      emojiPickerSelected,
      emojiIndex,
      toggle,
      convertEmoji,
    }
  },
}
</script>
