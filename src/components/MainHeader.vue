<script setup lang="ts">
import { ref } from 'vue'
import ModalDialog from '../components/ModalDialog.vue'

const showDialog = ref(false)
</script>

<template>
  <header class="w-full">
    <dev class="flex justify-between w-5/6 m-auto items-center" style="height: 118px">
      <div class="flex items-center">
        <img src="../assets/main-icon.png" alt="" class="w-20" />
        <div class="text-xl">
          <h2 class="font-bold uppercase">Snikers SHOP</h2>
          <p class="text-amber-950">Looking for a vehicle?</p>
        </div>
      </div>
      <ul class="flex items-center gap-10">
        <li class="flex items-center gap-3 hover:trgb(5, 97, 195) cursor-pointer">
          <v-switch label="Dark teme" class="flex" />
        </li>
        <li class="flex items-center gap-3 hover:text-white cursor-pointer">
          <img class="c-red" src="../../public/location.svg" />
          <b>Location</b>
        </li>
        <li class="flex items-center gap-3 hover:text-white cursor-pointer">
          <img class="c-red" src="../../public/profile.svg" />
          <b @click="showDialog = true">Profile</b>
        </li>
        <li class="flex items-center gap-3 hover:text-white cursor-pointer">
          <img class="c-red" src="../../public/cart.svg" />
          <b>Basket</b>
        </li>
        <li class="flex items-center gap-3 hover:text-white cursor-pointer">
          <img class="c-red" src="../../public/heart.svg" />
          <b>Like</b>
        </li>
        <li class="flex items-center gap-3 hover:text-black">
          <button class="rounded-full bg-slate-100 text-xl" style="width: 296px; height: 70px">
            Shoose a yacht
          </button>
        </li>
      </ul>
    </dev>
    <ModalDialog :is-show="showDialog" @update:isShow="showDialog = $event" />
  </header>
</template>
