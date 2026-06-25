<script setup>
defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickFavorite: Function,
  onClickAdd: Function,
})
</script>

<template>
  <div
    class="relative flex h-full cursor-pointer flex-col rounded-[40px] border border-[#f3f3f3] bg-white p-8 transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      v-if="onClickFavorite"
      class="absolute top-8 left-8"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="Like 2"
      @click="onClickFavorite"
    />

    <div class="flex h-52 w-full items-center justify-center">
      <img :src="imageUrl" alt="Sneakers" class="h-full object-contain" />
    </div>

    <p class="mt-2 text-slate-700">{{ title }}</p>

    <div class="mt-auto flex items-end justify-between pt-5">
      <div class="flex flex-col">
        <span class="text-xs text-[#BDBDBD] uppercase">Цена:</span>
        <b>{{ price }} руб.</b>
      </div>
      <img
        v-if="onClickAdd"
        @click="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
      />
    </div>
  </div>
</template>
