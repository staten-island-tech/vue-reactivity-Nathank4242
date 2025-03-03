<script setup></script>

<template>
  <main
    class="min-h-screen bg-gradient-to-b from-blue-100 to-blue-200 flex items-center justify-center text-center"
  >
    <div class="container px-4 py-10 bg-white rounded-xl shadow-lg max-w-3xl w-full">
      <h2 class="text-4xl font-extrabold text-blue-600 mb-4">
        Welcome to the <span class="text-yellow-500">Pokemon</span> Item Store
      </h2>
      <router-link to="/about">
        <button
          class="bg-yellow-500 text-white font-semibold py-2 px-6 rounded-md hover:bg-yellow-600 transition duration-300"
        >
          Start Shopping
        </button>
      </router-link>
    </div>
  </main>
</template>

<style scoped></style>
