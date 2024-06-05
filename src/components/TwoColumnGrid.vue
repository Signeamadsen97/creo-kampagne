<script setup>
const props = defineProps({
  firstColumnWidth: {
    type: String,
    default: "1fr",
  },
  secondColumnWidth: {
    type: String,
    default: "1.3fr",
  },
  gap: {
    type: String,
    default: "0",
  },
});
</script>

<template>
  <div class="grid">
    <slot name="col-1" />
    <slot name="col-2" />
  </div>
</template>

<style scoped lang="scss">
.grid {
  display: grid;
  grid-template-columns: v-bind(firstColumnWidth) v-bind(secondColumnWidth);
  gap: v-bind(gap);

  @media (max-width: 900px) {
    grid-template-columns: 1fr;
  }
}
</style>
