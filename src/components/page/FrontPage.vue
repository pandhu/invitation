<template>
  <div class="section min-h-screen flex lg:bg-cover bg-cover" :style="{ backgroundImage: backgroundImage && 'url(' + backgroundImage + ')' }">
    <div class="front-text-box lg:m-auto m-auto">
      <div>
        <img src="/src/assets/images/basmallah-dark.png" alt="" class="object-contain h-10 mx-auto my-8 lg:h-20 lg:mx-auto lg:my-16 animate__animated animate__fadeInDown">
      </div>
      <div class="tex-box-upper w-full text-base mb-8 lg:text-2xl lg:my-16  animate__animated animate__fadeInDown">
        WE ARE TYING THE KNOT
      </div>
      <div class="text-box-middle w-full text-5xl font-normal">
        <div class="lg:text-6xl name-bride mb-2 lg:my-16 animate__animated animate__fadeInLeft animate__delay-1s">
          Nilam
        </div>
        <div class="lg:text-6xl name-apersand lg:my-16 animate__animated animate__fadeIn animate__slow">
          &
        </div>
        <div class="lg:text-6xl name-groom lg:my-16 mt-2 animate__animated animate__fadeInRight animate__delay-1s">
          Pandhu
        </div>
      </div>
      <div class="lg:text-2xl tex-box-lower lg:my-16 w-full text-base mt-8 lg:text-2xl animate__animated animate__fadeInUp">
        09 . 10 . 2021
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

const backgroundImage = isMobile() ? '/src/assets/images/background-mobile.png' : '/src/assets/images/background-desktop.png'
const onmobile = isMobile()
</script>

<script>
function isMobile() {
  if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
     return true
   } else {
     return false
   }
}
</script>


<style scoped>
@font-face {
  font-family: "Bacalisties";
  src: url('../src/assets/fonts/Bacalisties.ttf');
}

@font-face {
  font-family: "Trajan Pro";
  font-weight: 600;
  src: url('../src/assets/fonts/TrajanPro-Bold.otf');
}

.front-text-box {
  color: #69765C  ;
}

.text-box-middle {
  font-family: "Bacalisties"
}

.tex-box-upper, .tex-box-lower {
  font-family: "Trajan Pro";
}
</style>
