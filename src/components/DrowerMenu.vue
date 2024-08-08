<script setup>
import CartItemList from '../components/CartItemList.vue'
</script>

<template>
  <div class="bg-black fixed top-0 left-0 z-10 h-full w-full opacity-70"></div>
  <div class="fixed top-0 right-0 bg-white w-96 h-full z-20 p-8">
    <h2 class="text-2xl font-bold">Basket</h2>
    <CartItemList />
  </div>
</template>
