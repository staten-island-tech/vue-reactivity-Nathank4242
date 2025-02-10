<template>
  <div class="card border-indigo-600 box-border min-h-max w-64 p-4 border-8 m-8">
    <h2 class="card-name text-blue-600 text-xl">{{ item.name }}</h2>
    <img :src="item.image" alt="" />
    <h3 class="card-name text-blue-600 text-xl">{{ item.price }}</h3>
    <button
      type="button"
      class="btn bg-blue-500 text-white p-2 rounded-md hover:bg-blue-700"
      id="add"
      @click="add"
    >
      Add To Cart
    </button>
    <button
      type="button"
      class="btn bg-blue-500 text-white p-2 rounded-md hover:bg-blue-700"
      id="Remove"
      @click="remove"
    >
      Remove From Cart
    </button>
  </div>
</template>

<script setup>
function removeCard(card) {
  card.remove()
}

defineProps({
  item: Object,
})
</script>

<style scoped></style>
