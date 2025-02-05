<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 p-6">
    <div
      class="card border-indigo-600 box-border min-h-max w-full p-6 border-8 shadow-lg rounded-lg"
    >
      <h2 class="card-name text-blue-600 text-xl font-semibold">{{ item.name }}</h2>
      <h3 class="card-price text-blue-500 text-lg mt-2">{{ item.price }}</h3>
    </div>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

<style scoped>
.card-name {
  font-weight: bold;
}

.card-price {
  font-size: 1.25rem;
}
</style>
