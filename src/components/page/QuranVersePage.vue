<template>
  <div class="section min-h-screen items-center flex">
    <div class="container m-auto">
      <div class="flower-container-box m-auto max-w-xs mt-10 mb-10">
        <img class="m-auto w-32" src="/src/assets/images/ornament-3.png">
      </div>
      <div class="quran-verse-container px-10 md:px-50">
        <div>
          <img src="/src/assets/images/an-nisa-arabic.png" alt="" class="mx-auto">
        </div>
        <div>
        <a class="text-sm md:text-3xl">
          “O humanity! Be mindful of your Lord Who created you from a single soul, and from it He created its mate, and through both He spread countless men and women. And be mindful of Allah—in Whose Name you appeal to one another—and ˹honour˺ family ties. Surely Allah is ever Watchful over you.”
        </a>
        </div>
        <div class="mt-4 font-bold md:text-2xl ">
          <a>
            QS. An-Nisa: 1
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<style scoped>
@font-face {
  font-family: "Open Sans";
  src: url('../src/assets/fonts/OpenSans-Regular.ttf');
}

.quran-verse-container {
  color: #69765C;
  font-family: 'Open Sans';
}
</style>
