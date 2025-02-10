<script setup>
import ItemCard from '../components/ItemCard.vue'
import items from '../assets/data.json'
</script>
<template>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>
  <div class="about flex justify-center bg-cyan-200">
    <h1>Welcome to Pokemon Center Item Shop</h1>
  </div>
  <RouterView />
  <button
    class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
  >
    Nothing button
  </button>
  <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 p-6">
    <ItemCard v-for="item in items" :key="item.name" :item="item" @click="console.log(item.name)" />
  </div>

  <div
    class="fixed top-0 right-0 w-80 h-full bg-gray-100 border-l-4 border-gray-600 p-4 overflow-y-auto"
  >
    <h1 class="text-center text-2xl font-bold mb-6">Cart</h1>
  </div>
</template>

<style>
nav {
  font-size: 12px;
}
</style>
