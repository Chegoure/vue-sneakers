<script setup>
import { onMounted, ref } from 'vue'
import axios from 'axios'

import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'

const items = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get('https://4af5d8fdd7738693.mokky.dev/items')
    items.value = data
  } catch (error) {
    console.log(error)
  }
})
</script>

<template>
  <!-- <Drawer /> -->
  <div class="m-auto mt-14 w-4/5 rounded-xl bg-white shadow-xl">
    <Header />

    <div class="p-10">
      <div class="flex items-center justify-between">
        <h2 class="mb-8 text-3xl font-bold">Все кроссовки</h2>

        <div class="flex gap-4">
          <select
            class="rounded-md border border-gray-200 px-3 py-2 outline-none"
          >
            <option>По названию</option>
            <option>По цене (дешевле)</option>
            <option>По цене (дороже)</option>
          </select>

          <div class="relative">
            <img class="absolute top-3 left-3" src="/search.svg" />
            <input
              class="rounded-md border border-gray-200 py-2 pr-4 pl-11 outline-none focus:border-gray-400"
              placeholder="Поиск..."
            />
          </div>
        </div>
      </div>

      <div class="mt-10">
        <CardList :items="items" />
      </div>
    </div>
  </div>
</template>
