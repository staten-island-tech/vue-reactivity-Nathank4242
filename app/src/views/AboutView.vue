<script setup>
import ItemCard from '../components/ItemCard.vue'
import CartItem from '../components/CartItem.vue'
import items from '../assets/data.json'
import { reactive } from 'vue'

const cart = reactive([])

const addToCart = (item) => {
  const existingItem = cart.find((cartItem) => cartItem.name === item.name)

  if (existingItem) {
    existingItem.quantity += 1
  } else {
    cart.push({ ...item, quantity: 1 })
  }
}

const removeFromCart = (item) => {
  const index = cart.findIndex((cartItem) => cartItem.name === item.name)
  if (index !== -1) {
    if (cart[index].quantity > 1) {
      cart[index].quantity -= 1
    } else {
      cart.splice(index, 1)
    }
  }
}

const getTotalPrice = () => {
  return cart.reduce((total, cartItem) => {
    const itemPrice = parseFloat(cartItem.price.replace('$', ''))
    return total + itemPrice * cartItem.quantity
  }, 0)
}

//math stuff 
const getTotalItems = () => {
  return cart.reduce((total, cartItem) => total + cartItem.quantity, 0)
}
</script>

<template>
  <header>
    <div class="bg-blue-600 p-4">
      <nav class="text-center">
        <RouterLink
          to="/"
          class="text-white text-lg font-semibold hover:text-yellow-400 transition duration-300"
        >
          Home
        </RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />

  <div class="flex flex-row">
    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6 p-6 w-full pr-80"
    >
      <ItemCard v-for="item in items" :key="item.name" :item="item">
        <button
          type="button"
          class="btn bg-blue-500 text-white p-2 rounded-md hover:bg-blue-700 w-full"
          id="add"
        >
          Add To Cart
        </button>
      </ItemCard>
    </div>

    <div
      class="cart fixed top-0 right-0 w-80 h-full bg-gray-100 border-l-4 border-gray-600 p-4 overflow-y-auto z-10"
    >
      <h1 class="text-center text-2xl font-bold mb-6">Cart</h1>

      <div v-if="cart.length === 0" class="text-center text-gray-600">Your cart is empty.</div>

      <div v-for="(cartItem, index) in cart" :key="index">
        <CartItem :item="cartItem" @remove="removeFromCart" />
      </div>

      <div v-if="cart.length > 0" class="text-center mt-6 font-bold">
        <p>Total Items: {{ getTotalItems() }}</p>
        <!-- Display total items -->
        <p>Total Price: ${{ getTotalPrice() }}</p>
      </div>
    </div>
  </div>
</template>

<style>
nav {
  font-size: 12px;
}
</style>
