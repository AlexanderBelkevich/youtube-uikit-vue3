<template>
  <div
    class="table-row"
    :style="{
      'grid-template-columns': columnTemplates,
      'background-color': bgRow}">
    <slot></slot>
  </div>
</template>

<script setup>
const props = defineProps({
  columnTemplates: {
    type: String,
    required: false
  },
  bgRow: {
    type: String,
    required: false
  }
})
</script>

<style lang="scss" scoped>
.table-row {
  border-bottom: 2px solid #EEEFF4;
  position: relative;
  display: grid;
  column-gap: 10px;
  align-items: center;
  padding: 0 16px;
  @media screen and (max-width: 767px) {
    display: block;
  }
  &:last-child {
    border-bottom: none;
  }
  &--items-center {
    justify-items: center;
  }
}
</style>