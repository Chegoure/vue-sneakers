<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'
</script>

<template>
  <div class="fixed top-0 left-0 z-10 h-full w-full bg-black opacity-70"></div>
  <div class="fixed top-0 right-0 z-20 h-full w-96 bg-white p-8">
    <DrawerHead />
    <CartItemList />

    <div class="mt-7 flex flex-col gap-4">
      <div class="flex gap-2">
        <span>Итого:</span>
        <div class="flex-1 border-b border-dashed border-[#DFDFDF]"></div>
        <b>12900 руб.</b>
      </div>

      <div class="flex gap-2">
        <span>Налог 5%:</span>
        <div class="flex-1 border-b border-dashed border-[#DFDFDF]"></div>
        <b>1074 руб.</b>
      </div>

      <button
        disabled=""
        class="mt-4 w-full cursor-pointer rounded-2xl bg-lime-500 py-3 text-white transition hover:bg-lime-600 active:bg-lime-700 disabled:bg-gray-300"
      >
        Оформить заказ
      </button>
    </div>
  </div>
</template>
