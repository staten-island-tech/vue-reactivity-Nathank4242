<template>
  <div class="cart-item border-b-2 py-4 flex justify-between items-center">
    <div class="flex items-center space-x-4">
      <div>
        <span class="font-semibold">{{ item.name }}</span
        ><br />
        <span class="text-gray-500 text-sm">{{ item.price }}</span>
      </div>

      <div>
        <span class="text-gray-700">Quantity: {{ item.quantity }}</span>
      </div>
    </div>

    <button
      class="text-white bg-red-500 hover:bg-red-600 rounded-md px-4 py-2 text-xs font-semibold transition-all duration-300 ml-4"
      @click="removeItem(item)"
    >
      Remove
    </button>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})

const emit = defineEmits()

const removeItem = (item) => {
  emit('remove', item)
}
</script>

<style scoped>
.cart-item {
  padding: 8px 0;
  border-bottom: 1px solid #ddd;
}
</style>
