<script setup lang="ts">
import FilterMenu from './FilterMenu.vue'
import ProductCard from './ProductCard.vue'
</script>

<template>
  <div class="w-4/5 bg-white mx-auto rounded-xl shadow-xl mt-14 p-10">
    <h2 class="text-3xl font-bold flex justify-center p-10">All snikers</h2>
    <div class="grid grid-cols-4 gap-5">
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
    </div>
  </div>
</template>
