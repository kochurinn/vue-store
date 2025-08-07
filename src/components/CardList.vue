<script setup>
import Card from './Сard.vue'
</script>

<template>
  <ul class="grid grid-cols-4 gap-10">
    <Card
      img-url="/sneakers/sneakers-1.jpg"
      title="Кроссовки"
      :price="12930"
      :is-favorite="false"
      :is-added="false"
    />
    <Card />
    <Card />
    <Card />
    <Card />
  </ul>
</template>
