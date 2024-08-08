<template>
  <v-layout style="height: 56px;">
    <v-bottom-navigation
      v-model="value"
      color="teal"
      class="rounded-lg border-inherit"
      style="position: relative"
      grow
    >
      <v-combobox
        label="Combobox"
        :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
        variant="solo"
      ></v-combobox>
      <v-combobox
        label="Combobox"
        :items="['California', 'Colorado', 'Florida', 'Georgia', 'Texas', 'Wyoming']"
        variant="solo"
      ></v-combobox>

      <v-btn class="rounded-lg border-inherit" v-for="btn in listBtn">
       <img src="" alt="" />
        {{ btn }}
      </v-btn>


    </v-bottom-navigation>
  </v-layout>
</template>

<script>
  export default {
    data () {
    return {
      listBtn: ['standart', 'classic', 'business', 'vip']
    }
    }
  }
</script>
