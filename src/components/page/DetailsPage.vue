<template>
  <div class="section flex min-h-screen	md:h-full md:min-h-screen outer-container pb-10 md:my-20 relative">
    <div class="container md:max-w-none">
        <div class="ornament-left absolute top-5 md:top-10 right-0">
            <img src="/src/assets/images/ornament-details-top.png" alt="" class="object-contain h-20 md:h-60">
          </div>
          <div class="ornament-right absolute bottom-5 md:bottom-10 left-0">
            <img src="/src/assets/images/ornament-details-bottom.png" alt="" class="object-contain h-20 md:h-60">
          </div>
      <div class="content-container md:w-3/4 mx-auto flex h-full items-center justify-center static  md:text-3xl">
        <div class="inner-container">
          <div class="greeting-container my-8 px-10 md:my-16 md:px-16">
            <a class="">We kindly request the honor of your presence and duas at our online</a>
          </div>
          <div class="akad-nikah"><a class="text-2xl px-5 pb-3 md:text-5xl border-b-2 md:px-10 md:pb-5">AKAD NIKAH</a></div>
          <div class="date my-5 md:my-8">
            <p class="p-1 md:p-3 justify-center">Saturday, 9th October 2021</p>
            <p class="p-1 md:p-3 justify-center">08.30 UTC+7</p>
          </div>
          <div class="zoom-container">
            <a href="https://bit.ly/AkadNilamPandhu" class="flex items-center justify-center dont-prevent"><img src="/src/assets/images/zoom-icon.png" alt="" class="mr-3"> <span class="inline-block align-middle bold underline">bit.ly/AkadNilamPandhu</span></a>
          </div>

          <Modal/>

          <div class="px-10 mt-5 md:px-16 md:mt-16">
            <a>We wish we could bring all of the people we love and care about together to celebrate our wedding, but with current situation, our wedding will include only immediate family members. We hope you will join us via Zoom for this special, happy occasion! </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'
import Modal from '../Modal.vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>

<style scoped>
@font-face {
  font-family: "Trajan Pro";
  src: url('../src/assets/fonts/TrajanPro-Bold.otf');
}

@font-face {
  font-family: "Open Sans";
  src: url('../src/assets/fonts/OpenSans-Regular.ttf');
}

.outer-container {
  background-color: #69765C  ;
}

a, p {
  color: white;
}

.greeting-container {
  font-family: "Open Sans";
}

.calendar-button > a {
  font-family: "Open Sans";
  color:#69765C;
  font-weight: bold;
  background-color: white;
}

.akad-nikah > a {
  font-family: "Trajan Pro";
}

.date > p {
  font-family: "Open Sans";
  font-weight: bold;
}

</style>
