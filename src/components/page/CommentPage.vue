<template>
  <div class="flex my-10">
    <div class="container m-auto">
      <div class="title-container mb-10">
        <a class="text-xl">Ucapan & Doa untuk Mempelai</a>
      </div>
      <div class="form-container p-6">
        <form class="w-full max-w-lg">
          <div class="flex flex-wrap -mx-3 mb-6">
            <div class="w-full px-3 mb-6">
              <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" id="grid-first-name" type="text" placeholder="Nama">
            </div>
            <div class="w-full px-3">
              <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white h-36" id="grid-last-name" type="text" placeholder="Pesan"></textarea>
            </div>
          </div>
        </form>
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

.google-map * {
  border-style: none;
}

a {
  font-family: "Open Sans";
  color: #69765C  ;
}
</style>
