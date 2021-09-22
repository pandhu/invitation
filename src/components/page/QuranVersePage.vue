<template>
  <div class="items-center flex">
    <div class="container m-auto">
      <div class="flower-container-box m-auto max-w-xs mt-10 mb-10 ">
        <img class="m-auto w-32" src="/src/assets/images/ornament-3.png">
      </div>
      <div class="quran-verse-container px-10 md:px-50">
        <div>
        <a class="md:text-xl">
          Wahai manusia, bertakwalah kepada Tuhanmu yang telah menciptakan kamu dari diri yang satu (Adam), dan (Allah) menciptakan pasangannya (Hawa), dari (diri)-nya; dan dari keduanya Allah memperkembangbiakkan laki-laki dan perempuan yang banyak. Bertakwalah kepada Allah yang dengan nama-Nya kamu saling meminta dan (jagalah) hubungan kekeluargaan. Sesungguhnya Allah selalu menjaga dan mengawasimu.
        </a>
        </div>
        <div class="mt-4 font-bold md:text-2xl">
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
