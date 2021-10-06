<template>
  <div class="section min-h-screen items-center flex py-10">
    <div class="flex-row h-full m-auto">
      <CountdownSection />
      <CommentSection />
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'
import CountdownSection from './CountdownSection.vue'
import CommentSection from './CommentSection.vue'

const datetime = 'Oct 9, 2021 09:00:00'

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
