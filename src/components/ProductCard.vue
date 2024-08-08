<script setup lang="ts">
import { defineProps } from 'vue'

defineProps<{
  img: string
  name: string
  price: string
}>()
</script>

<template>
  <div>
    <div
      class="relative p-10 bg-lime-200 cursor-pointer border border-slate-100 hover:-translate-y-2 hover:shadow rounded-3xl"
    >
      <div class="grid">
        <img src="/public/like-2.svg" alt="like" class="absolute top-18 left-8" />
        <div class="flex justify-center items-center">
          <img src="/public/sneakers/sneakers-1.jpg" alt="picture" class="rounded-xl" />
        </div>
      </div>

      <div class="flex justify-between">
        <div class="flex flex-col">
          <p class="text-gray-950">{{ name }}</p>
          <span class="text-slate-500 flex flex-col mt-5">Price:</span>
          <b>1500 $</b>
        </div>
        <img src="/public/plus.svg" alt="plus" />
      </div>
    </div>
  </div>
</template>
