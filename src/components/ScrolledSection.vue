<template>
  <section>
    <slot name="container" />
  </section>
</template>

<script setup lang="ts">
const props = defineProps({
  beginPosition: {
    type: Number,
    required: true,
  },
  sectionHeight: {
    type: Number,
    required: true,
  },
});
</script>

<style scoped></style>
