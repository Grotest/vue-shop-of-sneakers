<script setup lang="ts">
import MainHeader from './components/MainHeader.vue'
import MainSectionTop from './components/MainSectionTop.vue'
import MainContent from './components/MainContent.vue'
import ModalDialog from './components/ModalDialog.vue'
import DrowerMenu from './components/DrowerMenu.vue'
</script>

<template>
  <div>
    <MainHeader class="sticky z-10" />
    <MainSectionTop class="z-0" />
    <!-- <DrowerMenu /> -->
    <MainContent />
    <ModalDialog />
  </div>
</template>

<style scoped>
@media (min-width: 1024px) {
}
</style>
