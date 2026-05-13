<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItem from './CartItem.vue'
</script>

<template>
  <div class="fixed top-0 left-0 z-10 h-full w-full bg-black opacity-70"></div>
  <div class="fixed top-0 right-0 z-20 h-full w-96 bg-white p-8">
    <DrawerHead />

    <CartItem />
  </div>
</template>
