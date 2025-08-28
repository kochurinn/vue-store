<script setup>
import Card from './Сard.vue'

defineProps({
  items: Array,
})

const emit = defineEmits(['addToFavorite', 'addToCart'])
</script>

<template>
  <ul class="grid grid-cols-4 gap-10">
    <Card
      v-for="item in items"
      :key="item.id"
      :imgUrl="item.imageUrl"
      :title="item.title"
      :price="item.price"
      :isAdded="item.isAdded"
      :isFavorite="item.isFavorite"
      :onClickFavorite="() => emit('addToFavorite', item)"
      :onClickAdd="() => emit('addToCart', item)"
    />
  </ul>
</template>
