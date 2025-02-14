<script setup>
import ItemCard from '../components/ItemCard.vue'
// import ShopCard from '../components/ShopCard.vue'
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
  <div class="flex flex-row">
    <!-- Items Grid -->
    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 p-6 w-full pr-80"
    >
      <ItemCard v-for="item in items" :key="item.name" :item="item">
        <button
          type="button"
          class="btn bg-blue-500 text-white p-2 rounded-md hover:bg-blue-700 w-full"
          id="add"
          @click="console.log(item.name)"
        >
          Add To Cart
        </button>
      </ItemCard>
    </div>

    <div
      class="cart fixed top-0 right-0 w-80 h-full bg-gray-100 border-l-4 border-gray-600 p-4 overflow-y-auto z-10"
    >
      <h1 class="text-center text-2xl font-bold mb-6">Cart</h1>
    </div>
  </div>
</template>

<style>
nav {
  font-size: 12px;
}
</style>
