<template>
  <div>
    <h2>{{ item.name }}</h2>
    <h2>{{ item.other }}</h2>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

<style scoped></style>
