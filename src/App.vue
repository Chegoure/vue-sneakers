<script setup>
import Header from './components/Header.vue'
import CardList from './components/CardList.vue'
import Drawer from './components/Drawer.vue'
</script>

<template>
  <Drawer />
  <div class="m-auto mt-14 w-4/5 rounded-xl bg-white shadow-xl">
    <Header />

    <div class="p-10">
      <h2 class="mb-8 text-3xl font-bold">Все кроссовки</h2>
      <CardList />
    </div>
  </div>
</template>
