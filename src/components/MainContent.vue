<script setup lang="ts">
import FilterMenu from './FilterMenu.vue'
import ProductCard from './ProductCard.vue'
</script>

<template>
  <div class="w-4/5 bg-white mx-auto rounded-xl shadow-xl mt-14 p-10">
    <div class="flex justify-between m-5">
      
        <h2 class="text-3xl font-bold flex justify-center">All snikers</h2>
        <select class="border border-gray-300 py-2 pl-10 pr-5 h-10 rounded-xl outline-none focus:border-transparent focus:ring-2 focus:ring-gray-600 w-1/4 bg-white appearance-none">
            <option disabled selected value="">Select....</option>
            <option>min price</option>
            <option>max price</option>
            <option>name</option>
        </select>

       
      <div class="relative">
        <img
          class="absolute left-4 top-3"
          src="../../public/search.svg"
        />
        <input 
          class="border border-gray-300 py-2 pl-10 pr-5 h-10 rounded-xl outline-none focus:border-transparent focus:ring-2 focus:ring-gray-600 "
          type="text"
          placeholder="Search"
        />
      </div>

    </div>

    <div class="grid grid-cols-4 gap-5">
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
      <ProductCard name="Boots" />
    </div>
  </div>
</template>
