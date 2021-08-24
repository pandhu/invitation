<template>
  <div class="flex mt-10">
    <div class="container m-auto">
      <div class="img-container mb-16">
        <img src="/src/assets/images/ilustrasi.png" alt="">
      </div>
      <div class="name-container">
        <div class="bride-container">
          <div class="bride-name-container p-3">
            <a class="text-3xl">Nilamsari Putri Utami</a>
          </div>
          <div class="bride-parents-name-container">
            <a>Putri pertama dari</a><br/>
            <a>Bpk. Suwardi & Ibu Julaeha</a>
          </div>
        </div>
        <div class="middle-container my-8">
          <a>DENGAN</a>
        </div>
        <div class="groom-container">
          <div class="groom-name-container mb-3">
            <a class="text-3xl">Pandhu Hutomo Aditya</a>
          </div>
          <div class="groom-parents-name-container">
            <a>Putra pertama dari</a><br/>
            <a>Bpk. Rohadi & Ibu Endang Winarsih</a>
          </div>
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
  font-family: "Bacalisties";
  src: url('../src/assets/fonts/Bacalisties.ttf');
}

@font-face {
  font-family: "Trajan Pro";
  font-weight: 600;
  src: url('../src/assets/fonts/TrajanPro-Bold.otf');
}

@font-face {
  font-family: "Open Sans";
  src: url('../src/assets/fonts/OpenSans-Regular.ttf');
}

a {
  color: #69765C  ;
}

.bride-name-container, .groom-name-container{
  font-family: "Bacalisties";
}

.bride-parents-name-container, .groom-parents-name-container{
  font-family: "Open Sans";
}

.middle-container {
  font-family: "Trajan Pro" ;
}
</style>
