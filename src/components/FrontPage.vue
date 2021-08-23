<template>
  <div class="h-screen flex" style="background-image: url('/src/assets/images/background-mobile.png')">
    <div class="front-text-box m-auto">
      <div class="tex-box-upper w-full text-base mb-8">
        UNDANGAN PERNIKAHAN
      </div>
      <div class="text-box-middle w-full text-5xl font-normal">
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
      <div class="tex-box-lower w-full text-base mt-8">
        09 . 10 . 2021
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
