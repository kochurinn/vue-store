<script setup>
import CartItemList from './CartItemList.vue'
</script>

<template>
  <div class="bg-black opacity-50 size-full absolute z-1 top-0 left-0"></div>
  <div class="bg-white w-120 absolute top-0 right-0 z-1 h-screen p-10">
    <h2 class="font-bold text-3xl mb-10">Корзина</h2>

    <CartItemList />

    <div class="absolute bottom-10 left-10 right-10">
      <div class="flex justify-between mb-5">
        <span>Итого</span>
        <span class="flex-1 border-b border-dashed mb-[6px] mx-3"></span>
        <span>21 498 руб.</span>
      </div>
      <div
        class="order_button flex p-4 justify-center rounded-2xl text-white font-bold bg-[#9dd458] items-center relative"
      >
        <span>Оформить заказ</span>
        <img class="absolute right-7" src="/arrow-next.svg" alt="" />
      </div>
    </div>
  </div>
</template>
