<template>
  <inline-svg
    :title="addTitle(props.fileName)"
    :src="require(`@/assets/icons/${checkFileName(props.fileName)}.svg`)"
    fill="currentColor"
  />
</template>

<script setup>
import InlineSvg from 'vue-inline-svg'

const props = defineProps({
  fileName: {
    type: String,
    default: ''
  }
})

const checkFileName = (str) => {
  if (!str) return str
  return str.toLowerCase().slice()
}
const addTitle = (str) => {
  if (!str) return str
  return str[0].toUpperCase() + str.slice(1)
}
</script>
