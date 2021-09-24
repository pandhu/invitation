<template>
  <div class="py-3 container px-3 text-left shadow-md rounded mb-3 md:mb-5">
    <div class="author-container mb-2"><a class="font-bold">{{ author }}</a></div>
    <div class="comment-container"><a>{{ comment }}</a></div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

const props = defineProps({
  author: String,
  comment: String
})

</script>

<style scoped>
@font-face {
  font-family: "Open Sans";
  src: url('../src/assets/fonts/OpenSans-Regular.ttf');
}

a {
  font-family: "Open Sans";
  color: #69765C  ;
}

.container {
  background-color: #f8f8f8;
}
</style>
