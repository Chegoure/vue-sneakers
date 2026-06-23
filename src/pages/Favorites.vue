<script setup>
import axios from 'axios'
import { ref, onMounted } from 'vue'
import CardList from '../components/CardList.vue'

const favorites = ref([])

onMounted(async () => {
  try {
    const { data } = await axios.get(
      'https://4af5d8fdd7738693.mokky.dev/favorites?_relations=items',
    )
    favorites.value = data.map((obj) => obj.item)
    console.log(favorites.value)
  } catch (err) {
    console.log(err)
  }
})
</script>

<template>
  <h2 class="mb-8 text-3xl font-bold">Мои закладки</h2>

  <CardList :items="favorites" is-favorites />
</template>
