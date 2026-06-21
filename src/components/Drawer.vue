<script setup>
import DrawerHead from './DrawerHead.vue'
import CartItemList from './CartItemList.vue'
import InfoBlock from './InfoBlock.vue'

const emit = defineEmits('createOrder')

const props = defineProps({
  totalPrice: Number,
  vatPrice: Number,
  buttonDisabled: Boolean,
})
</script>

<template>
  <div class="fixed top-0 left-0 z-10 h-full w-full bg-black opacity-70"></div>
  <div class="fixed top-0 right-0 z-20 h-full w-96 bg-white p-8">
    <DrawerHead />

    <div v-if="!totalPrice" class="flex h-full items-center">
      <InfoBlock
        title="Корзина пустая"
        description="Добавьте хотя бы одну пару кроссовок, чтобы сделать заказ."
        image-url="/package-icon.png"
      />
    </div>

    <div v-else>
      <CartItemList />

      <div class="mt-7 flex flex-col gap-4">
        <div class="flex gap-2">
          <span>Итого:</span>
          <div class="flex-1 border-b border-dashed border-[#DFDFDF]"></div>
          <b>{{ totalPrice }} руб.</b>
        </div>

        <div class="flex gap-2">
          <span>Налог 5%:</span>
          <div class="flex-1 border-b border-dashed border-[#DFDFDF]"></div>
          <b>{{ vatPrice }} руб.</b>
        </div>

        <button
          @click="emit('createOrder')"
          :disabled="buttonDisabled"
          class="mt-4 w-full cursor-pointer rounded-2xl bg-lime-500 py-3 text-white transition hover:bg-lime-600 active:bg-lime-700 disabled:bg-gray-300"
        >
          Оформить заказ
        </button>
      </div>
    </div>
  </div>
</template>
