<template>
  <div class="section flex py-10">
    <div class="container m-auto">
      <div class="title-container mb-10">
        <a class="text-2xl">COUNTING DOWN TO THE BIG DAY</a>
      </div>
      <div class="maps-container p-3">
        <iframe class="w-full" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3965.2996005293608!2d106.8513650158951!3d-6.355249763945358!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e69ec5cb41ed3df%3A0xdfd6d8d2eb933747!2sRumah%20Makan%20Lesehan%20Pondok%20Laras!5e0!3m2!1sen!2sid!4v1629814565739!5m2!1sen!2sid" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
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

@font-face {
  font-family: "Trajan Pro";
  font-weight: 600;
  src: url('../src/assets/fonts/TrajanPro-Bold.otf');
}

.title-container > a {
  font-family: "Trajan Pro";
  color: #69765C;
}

.google-map * {
  border-style: none;
}

.map-container{
    overflow:hidden;
    padding-bottom:56.25%;
    position:relative;
    height:0;
}

.map-container iframe{
    left:0;
    top:0;
    height:100%;
    width:100%;
    position:absolute;
}
</style>
