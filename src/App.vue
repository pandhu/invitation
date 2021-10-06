<template>
  <FrontPage />
  <QuranVersePage />
  <BrideGroomPage />
  <DetailsPage />
  <CountdownAndCommentPage />
  <CommentListPage />
  <FooterPage />
</template>

<script setup>
import FrontPage from './components/page/FrontPage.vue'
import QuranVersePage from './components/page/QuranVersePage.vue'
import BrideGroomPage from './components/page/BrideGroomPage.vue'
import DetailsPage from './components/page/DetailsPage.vue'
import CommentListPage from './components/page/CommentListPage.vue'
import FooterPage from './components/page/FooterPage.vue'
import CountdownAndCommentPage from './components/page/CountdownAndCommentPage.vue'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
</script>
<script>
export default {
  data() {
    return {
      isMusicPlay: false,
      isPaused: false,
    }
  },
  methods: {
    scrollHandler(e){
      if(!this.isMusicPlay && !this.isPaused) {
        const x = document.getElementById("audio");
        this.isMusicPlay = true
        x.play()
      }
    }
  },
  mounted(){
    const vid = document.getElementById("audio");
    vid.onpause = function() {
      this.isMusicPlay = false
      this.isPaused = true
    };

    vid.onplay = function() {
      this.isMusicPlay = true
      this.isPaused = false
    };
  },
  created() {
    window.addEventListener('DOMMouseScroll', this.scrollHandler);  // Mozilla Firefox
    window.addEventListener('mousewheel', this.scrollHandler, { passive: false }); // Other browsers

    window.addEventListener('touchstart', this.scrollHandler, { passive: false }); // mobile devices
    window.addEventListener('touchmove', this.scrollHandler, { passive: false }); // mobile devices
  },
  destroyed() {
    window.removeEventListener('mousewheel', this.scrollHandler, { passive: false });  // Other browsers
    window.removeEventListener('DOMMouseScroll', this.scrollHandler); // Mozilla Firefox

    window.removeEventListener('touchstart', this.scrollHandler); // mobile devices
    window.removeEventListener('touchmove', this.scrollHandler); // mobile devices
  }
}

function findElementByClass(elements, className){
  const found = elements.find(element => {
    if(typeof element.className !== 'undefined' && element.className.includes(className)) return true
  })
  return found
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
