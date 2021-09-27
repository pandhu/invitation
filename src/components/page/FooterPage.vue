<template>
  <div class="section items-center flex mb-5">
    <div class="container m-auto">
      <div class="flower-container-box m-auto max-w-xs mt-10">
        <img class="m-auto w-32" src="/src/assets/images/ornament-1.png">
      </div>
      <div class="footer-text-container">
        <p>With love,</p>
        <p>Nilam & Pandhu</p>
      </div>
    </div>
  </div>
  <div>
         <audio id="audio" autoplay class="m-auto">
          <source src="/src/assets/bgm/euphoria-piano.mp3" type="audio/mpeg">
        </audio>
      </div>
  <div>
    <p class="text-sm my-3">BGM: <a href="https://www.youtube.com/watch?v=jxgXDXw0g3o">BTS Euphoria - Piano Cover by DooPiano</a></p>
  </div>
  <div class="bottom h-7">

  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

defineProps({
  msg: String
})

const state = reactive({ count: 0 })
</script>
<script>

</script>

<style scoped>
@font-face {
  font-family: "Open Sans";
  src: url('../src/assets/fonts/OpenSans-Regular.ttf');
}
p {
  font-family: "Open Sans";
  color: #69765C  ;
}

.bottom{
  background-color: #69765C;
}
</style>
