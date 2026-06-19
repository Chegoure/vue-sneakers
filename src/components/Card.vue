<script setup>
defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
})

const emit = defineEmits(['onClickFavorite', 'onClickAdd'])
</script>

<template>
  <div
    class="relative cursor-pointer rounded-[40px] border border-[#F3F3F3] bg-white p-8 transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img src="/like-2.svg" />

    <img
      class="absolute top-8 left-8"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="Like 2"
      @click="emit('onClickFavorite')"
    />

    <img :src="imageUrl" alt="Sneakers" />
    <p class="mt-2">{{ title }}</p>

    <div class="mt-5 flex justify-between">
      <div class="flex flex-col">
        <span class="text-[#BDBDBD] uppercase">Цена:</span>
        <b>{{ price }} руб.</b>
      </div>
      <img
        @click="emit('onClickAdd')"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
      />
    </div>
  </div>
</template>
