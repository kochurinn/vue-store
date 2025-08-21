<script setup>
import { onMounted, reactive, ref, watch } from 'vue'
import axios from 'axios'

import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
// import Drawer from './components/Drawer.vue'

const items = ref([])

const filters = reactive({
  sortBy: 'title',
  searchQuery: '',
})

const onChangeSelect = (event) => {
  filters.sortBy = event.target.value
}

const onChangeInput = (event) => {
  filters.searchQuery = event.target.value
}

const fetchFavourites = async () => {
  try {
    const { data: favorites } = await axios.get('https://56036e980bcb4afb.mokky.dev/favorites')

    items.value = items.value.map(item => {
      const favorite = favorites.find(favorite => favorite.parentId === item.id)

      if (!favorite) {
        return item
      }

      return {
        ...item,
        isFavorite: true,
        favoriteId: favorite.id
      }
    })
    console.log(items.value)
  } catch (err) {
    console.log(err)
  }
}

const fetchItems = async () => {
  try {
    const params = {
      sortBy: filters.sortBy
    }

    if (filters.searchQuery) {
      params.title = `*${filters.searchQuery}*`
    }

    const {data} = await axios.get(`https://56036e980bcb4afb.mokky.dev/items`, {
      params
    })
    items.value = data.map(obj => {
      return {
        ...obj,
        isFavourite: false,
        isAdded: false,
      }
    })
  } catch (err) {
    console.log(err)
  }
}

watch(filters, fetchItems)
onMounted(async () => {
  await fetchItems()
  await fetchFavourites()
})
</script>

<template>
  <body class="w-[1150px] m-auto">
    <!-- <Drawer /> -->

    <Header />

    <div class="flex justify-between items-center mt-10">
      <h1 class="text-3xl font-bold">Все кроссовки</h1>
      <div class="flex">
        <select @change="onChangeSelect" class="py-2 px-3 border rounded-md outline-none mr-5">
          <option value="name">По названию</option>
          <option value="price">По возрастанию</option>
          <option value="-price">По убыванию</option>
        </select>
        <div class="relative">
          <img class="absolute left-4 top-3" src="/search.svg" alt="" />
          <input
            @input="onChangeInput"
            type="text"
            placeholder="Поиск..."
            class="border rounded-md py-2 pl-10 pr-4 outline-none focus:border-gray-400"
          />
        </div>
      </div>
    </div>

    <main class="mt-10">
      <CardList :items="items" />
    </main>
  </body>
</template>

<style scoped></style>
