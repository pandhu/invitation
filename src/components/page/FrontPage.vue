<template>
  <div class="h-screen flex md:bg-cover" :style="{ backgroundImage: backgroundImage.src && 'url(' + backgroundImage.src + ')' }">
    <div class="front-text-box m-auto">
      <div class="tex-box-upper w-full text-base mb-8 md:text-2xl">
        UNDANGAN PERNIKAHAN
      </div>
      <div class="text-box-middle w-full text-5xl md:text-7xl font-normal">
        <div class="name-bride mb-2">
          Nilam
        </div>
        <div class="name-apersand">
          &
        </div>
        <div class="name-groom mt-2">
          Pandhu
        </div>
      </div>
      <div class="tex-box-lower w-full text-base mt-8 md:text-2xl">
        09 . 10 . 2021
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

const backgroundImage = reactive({
  src: '/src/assets/images/background-desktop.png'
})
</script>

<script>

export default {
  beforeCreate() {
    console.log("ehe")
    let screenWidth = screen.width
    console.log(screenWidth)
    if(screenWidth < 1080){
      this.backgroundImage.src = '/src/assets/images/background-mobile.png'
    }
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
