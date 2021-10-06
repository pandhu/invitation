<template>
  <div class="section min-h-screen items-center flex">
    <div class="container m-auto lg:w-1/2">
      <div class="flower-container-box m-auto max-w-xs">
        <img class="m-auto w-32" src="/src/assets/images/ornament-3.png">
      </div>
      <div class="quran-verse-container lg:px-50">
        <div>
          <img :src="quranArabic" alt="" class="mx-auto px-2">
        </div>
        <div class="px-10">
        <a class="text-sm md:text-lg lg:text-xl lg:leading-9">
          “O humanity! Be mindful of your Lord Who created you from a single soul, and from it He created its mate, and through both He spread countless men and women. And be mindful of Allah—in Whose Name you appeal to one another—and ˹honour˺ family ties. Surely Allah is ever Watchful over you.”
        </a>
        </div>
        <div class="mt-4 font-bold lg:text-2xl ">
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
const quranArabic = isMobile() ? '/src/assets/images/an-nisa-arabic-mobile.png' : '/src/assets/images/an-nisa-arabic.png'

const state = reactive({ count: 0 })
</script>

<script>
function isMobile() {
  if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
     return true
   } else {
     return false
   }
}</script>

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
