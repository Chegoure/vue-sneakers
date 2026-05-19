<script setup>
import Card from './Card.vue'

const onClickAdd = () => {
  alert(123)
}
</script>

<template>
  <div class="grid grid-cols-4 gap-5">
    <Card
      imageUrl="/sneakers/sneakers-1.jpg"
      title="Мужские Кроссовки Nike Blazer Mid Suede"
      :price="12990"
      :onClickAdd
    />
  </div>
</template>
