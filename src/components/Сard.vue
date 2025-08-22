<script setup>
defineProps({
  title: String,
  imgUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
})
</script>

<template>
  <li class="product_card border rounded-xl w-3xs p-5 relative">
    <img
      :src="isFavorite ? '/like-2.svg' : '/like-1.svg'"
      alt=""
      class="absolute left-5 top-5"
      @click="onClickFavorite"
    />
    <img class="w-50 m-auto" :src="imgUrl" alt="" />
    <div class="title mt-8">{{ title }}</div>
    <div class="flex justify-between mb-5 mt-5">
      <div class="price flex flex-col">
        <span>Цена:</span><span class="font-bold">{{ price }} руб.</span>
      </div>
      <img :src="isAdded ? '/checked.svg' : '/plus.svg'" alt="" />
    </div>
  </li>
</template>
