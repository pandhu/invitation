<template>
  <div class="section flex min-h-screen	lg:h-full lg:min-h-screen outer-container pb-10 lg:py-20 relative">
    <div class="container lg:max-w-none">
        <div class="ornament-left absolute top-5 lg:top-10 right-0 z-0">
            <img src="/src/assets/images/ornament-details-top.png" alt="" class="object-contain h-12 md:h-24 lg:h-40">
          </div>
          <div class="ornament-right absolute bottom-5 lg:bottom-10 left-0">
            <img src="/src/assets/images/ornament-details-bottom.png" alt="" class="object-contain h-12 md:h-24 lg:h-40">
          </div>
      <div class="content-container md:w-3/4 lg:w-1/2 mx-auto flex h-full items-center justify-center static md:text-xl lg:text-3xl">
        <div class="inner-container">
          <div class="greeting-container my-8 px-10 md:my-12 md:px-12 lg:my-5 lg:px-5 z-10 lg:text-xl">
            <a class="">We kindly request the honor of your presence and duas at our online</a>
          </div>
          <div class="akad-nikah"><a class="text-2xl px-5 pb-3 lg:text-3xl border-b-2 lg:px-5 lg:pb-5">AKAD NIKAH</a></div>
          <div class="date my-5 lg:my-10">
            <p class="p-1 lg:p-1 justify-center lg:text-xl">Saturday, 9th October 2021</p>
            <p class="p-1 lg:p-1 justify-center lg:text-xl">08.30 AM UTC+7</p>
             <div class="zoom-container w-full">
              <a href="https://bit.ly/AkadNilamPandhu" class="flex items-center justify-center dont-prevent lg:text-xl mx-auto"><img src="/src/assets/images/zoom-icon.png" alt="" class="mr-3"> <span class="inline-block align-middle bold underline">bit.ly/AkadNilamPandhu</span></a>
            </div>
          </div>


          <Modal/>

          <div class="my-10 px-10 md:my-12 md:px-12 lg:my-5 lg:px-5 z-10 lg:text-xl">
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

.zoom-container > a{
  width: fit-content;
}

.zoom-container > a > span {
  font-family: "Open Sans";
  font-weight: bold;
}
</style>
