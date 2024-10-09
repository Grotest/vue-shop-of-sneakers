<script setup>
import CartItemList from '../components/CartItemList.vue'
</script>

<template>
  <div class="bg-black fixed top-0 left-0 z-10 h-full w-full opacity-70"></div>
  <div class="fixed top-0 right-0 bg-white w-96 h-full z-20 p-8">
    <h2 class="text-2xl font-bold">Basket</h2>
    <CartItemList />

    <div class="flex flex-col mb-3 my-5">
      <div class="flex gap-2">
        <Span>Total:</Span>
        <div class="border-b border-dashed flex-1"></div>
        <b>1235 $</b>
      </div>
      <div class="flex gap-2">
        <Span>Tax 5%:</Span>
        <div class="border-b border-dashed flex-1"></div>
        <b>1235 $</b>
      </div>
    </div>

    <button 
      class="bg-green-500 transition hover:bg-green-800 active:bg-green-950 w-full
      rounded-xl py-3 disabled:bg-slate-300 cursor-pointer"
      disabled="true">
      Order 
    </button>


  </div>
</template>
