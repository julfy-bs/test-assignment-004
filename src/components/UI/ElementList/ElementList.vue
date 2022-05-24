<template>
  <ul class="list">
    <li
      v-for="item in list"
      :key="item.id"
      class="list__item"
    >
      <element-svg
        file-name="tick"
        class="list__style"
      />
      {{ item }}
      <slot />
    </li>
  </ul>
</template>

<script setup>
import ElementSvg from '@/components/UI/ElementSvg/ElementSvg'

const props = defineProps({
  list: {
    type: Array,
    default: () => []
  }
})
</script>

<style lang="scss" scoped>
.list {
  display: flex;
  flex-flow: column nowrap;
  gap: 20px;
  list-style: none;
  margin: 0 0 0 30px;
  max-width: 500px;

  .list__item {
    position: relative;

    .list__style {
      color: var(--c-green);
      position: absolute;
      top: 10px;
      left: -30px;
    }
  }
}
</style>
