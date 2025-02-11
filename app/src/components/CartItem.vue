<template>
  <div class="Cart-Card border-indigo-600 box-border min-h-max w-64 p-4 border-8 m-8">
    <h2 class="card-name text-blue-600 text-xl">{{ item.name }}</h2>
    <slot></slot>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

<style scoped></style>
