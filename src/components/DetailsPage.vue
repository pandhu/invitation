<template>
  <div class="flex h-screen outer-container">
    <div class="container">
      <div class="top-container flex mt-5">
        <div class="ornament-left">
          <img src="/src/assets/images/ornament-4-left.png" alt="" class="object-contain h-28">
        </div>
        <div class="basmallah-container flex-grow ">
          <a>placeholder basmallah</a>
        </div>
        <div class="ornament-right">
          <img src="/src/assets/images/ornament-4-right.png" alt="" class="object-contain h-28">
        </div>
      </div>
      <div class="greeting-container my-8 px-10">
        <a class="italic">Assalamualaikum Warahmatullahi Wabarakatuh</a>
      </div>
      <div class="greeting-container px-10">
        <a>Dengan memohon ridho dan rahmat Allah SWT, kami bermaksud menyelenggarakan Syukkuran Pernikahan putra putri kami yang insyaAllah akan diselenggarakan pada:</a>
      </div>

      <div class="date-container my-10">
        <a class="p-3"> Sabtu, 9 Oktober 2021</a>
      </div>

      <div class="time-container flex divide-x divide-white-500">
        <div class="akad-time-container flex-1">
          <a class="font-bold	">Akad Nikah</a><br>
          <a>09.00 WIB</a>
        </div>
        <div class="resepsi-time-container flex-1">
          <a class="font-bold	">Resepsi</a><br>
          <a>11.00-13.00 WIB</a>
        </div>
      </div>

      <div class="place-container px-10 mt-10">
        <a class="font-bold">Pondok Laras</a><br>
        <a>Jl. Akses UI No.2 Tugu, Kec. Cimanggis, Kota Depok, Jawa Barat</a>
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

a {
  color: white;
}

.greeting-container {
  font-family: "Open Sans";
}

.date-container > a {
  font-family: "Trajan Pro";
  color:#69765C;
  background-color: white;
}


</style>
