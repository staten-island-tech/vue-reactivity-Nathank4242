<script>
import ItemCard from '../components/ItemCard.vue'

const items = [
  { name: 'number1', other: 'other1' },
  { name: 'number2', other: 'other2' },
]
</script>

<template>
  <main>
    <ItemCard v-for="item in items" :key="item.name" :item="item" />
  </main>
  <header>
    <div class="wrapper">
      <nav>
        <RouterLink to="/">Home</RouterLink>
      </nav>
    </div>
  </header>
  <div class="about flex justify-center bg-cyan-200">
    <h1>Welcome to the page</h1>
  </div>
  <RouterView />
  <button
    class="bg-transparent hover:bg-blue-500 text-blue-700 font-semibold hover:text-white py-2 px-4 border border-blue-500 hover:border-transparent rounded"
  >
    Button
  </button>
</template>

<style>
nav {
  font-size: 12px;
}
</style>
