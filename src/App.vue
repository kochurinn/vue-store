<script setup>
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'
</script>

<template>
  <body class="w-[1150px] m-auto">
    <Drawer />

    <Header />

    <div class="flex justify-between items-center mt-10">
      <h1 class="text-3xl font-bold">Все кроссовки</h1>
      <div class="flex">
        <select class="py-2 px-3 border rounded-md outline-none mr-5">
          <option>По названию</option>
          <option>По возрастанию</option>
          <option>По убыванию</option>
        </select>
        <div class="relative">
          <img class="absolute left-4 top-3" src="/search.svg" alt="" />
          <input
            type="text"
            placeholder="Поиск..."
            class="border rounded-md py-2 pl-10 pr-4 outline-none focus:border-gray-400"
          />
        </div>
      </div>
    </div>

    <main class="mt-10">
      <CardList />
    </main>
  </body>
</template>

<style scoped></style>
