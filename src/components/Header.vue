<script setup>
const emit = defineEmits(['toggleDrawer'])
</script>

<template>
  <header class="p-10 flex border rounded-xl items-center justify-between">
    <div class="logo">
      <img src="../../public/logo.png" alt="" />
    </div>
    <div class="menu flex w-90 justify-between">
      <div @click="() => emit('toggleDrawer')" class="basket flex cursor-pointer">
        <img src="../../public/cart.svg" alt="" />
        1234 руб.
      </div>
      <div class="favourites flex">
        <img src="../../public/heart.svg" alt="" />
        Закладки
      </div>
      <div class="profile flex">
        <img src="../../public/profile.svg" alt="" />
        Профиль
      </div>
    </div>
  </header>
</template>
