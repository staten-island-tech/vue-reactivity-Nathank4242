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
    Button
  </button>
  <ItemCard v-for="item in items" :key="item.name" :item="item" />
</template>

<style>
nav {
  font-size: 12px;
}
</style>
