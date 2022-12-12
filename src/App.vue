<template>
  <AppPickerComposition />
</template>

<script>
import 'emoji-mart-vue-fast/css/emoji-mart.css'
// Note: component needs to be imported from /src subfolder:
import AppPickerComposition from './AppPickerComposition'

export default {
  name: 'App',
  components: {
    AppPickerComposition,
  },
}
</script>
