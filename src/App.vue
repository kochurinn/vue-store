<script setup>
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'
</script>

<template>
  <body class="w-[1150px] m-auto">
    <Drawer />

    <Header />

    <h1 class="text-3xl font-bold mt-10">Все кроссовки</h1>

    <main class="mt-10">
      <CardList />
    </main>
  </body>
</template>

<style scoped></style>
