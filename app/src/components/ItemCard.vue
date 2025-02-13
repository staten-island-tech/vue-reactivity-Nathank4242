<template>
  <div class="card border-indigo-600 box-border min-h-max w-full sm:w-64 p-4 border-8 m-8">
    <h2 class="card-name text-blue-600 text-xl">{{ item.name }}</h2>
    <img :src="item.image" alt="" class="w-full h-auto" />
    <h3 class="card-name text-blue-600 text-xl">{{ item.price }}</h3>
    <slot></slot>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

<style scoped></style>
