<script setup>
import Card from './Сard.vue'

defineProps({
  items: Array,
})

const emit = defineEmits(['addToFavorite'])
</script>

<template>
  <ul class="grid grid-cols-4 gap-10">
    <Card
      v-for="item in items"
      :key="item.id"
      :img-url="item.imageUrl"
      :title="item.title"
      :price="item.price"
      :is-added="false"
      :isFavorite="item.isFavorite"
      :onClickFavorite="() => emit('addToFavorite', item)"
    />
  </ul>
</template>
