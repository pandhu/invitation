<template>
  <FrontPage />
  <QuranVersePage />
  <BrideGroomPage />
  <DetailsPage />
  <CountDownPage />
  <CommentPage />
  <CommentListPage />
  <FooterPage />
</template>

<script setup>
import FrontPage from './components/page/FrontPage.vue'
import QuranVersePage from './components/page/QuranVersePage.vue'
import BrideGroomPage from './components/page/BrideGroomPage.vue'
import DetailsPage from './components/page/DetailsPage.vue'
import CountDownPage from './components/page/CountDownPage.vue'
import CommentPage from './components/page/CommentPage.vue'
import CommentListPage from './components/page/CommentListPage.vue'
import FooterPage from './components/page/FooterPage.vue'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
</script>
<script>
export default {
  data() {
    return {
      inMove: false,
      activeSection: 0,
      offsets: [],
      touchStartY: 0,
      lastScrollTop: 0,
      isMusicPlay: false,
    }
  },
  methods: {
    calculateSectionOffsets() {
      this.offsets = []
      let sections = document.getElementsByClassName('section');

      let length = sections.length;

      for(let i = 0; i < length; i++) {
        let sectionOffset = sections[i].offsetTop;
        this.offsets.push(sectionOffset);
      }
    },
    handleMouseWheel: function(e) {

      if (e.wheelDelta < 30 && !this.inMove) {
        this.moveUp();
      } else if (e.wheelDelta > 30 && !this.inMove) {
        this.moveDown();
      }

      e.preventDefault();
      return false;
    },
    handleMouseWheelDOM: function(e) {

      if (e.detail > 0 && !this.inMove) {
        this.moveUp();
      } else if (e.detail < 0 && !this.inMove) {
        this.moveDown();
      }

      return false;
    },
    moveDown() {
      this.inMove = true;
      this.activeSection--;

      if(this.activeSection < 0) this.activeSection = 0;

      this.scrollToSection(this.activeSection, true);
    },
    moveUp() {
      this.inMove = true;
      this.activeSection++;

      if(this.activeSection > this.offsets.length - 1) this.activeSection = this.offsets.length - 1;

      this.scrollToSection(this.activeSection, true);
    },
    scrollToSection(id, force = false) {
      if(this.inMove && !force) return false;

      this.activeSection = id;
      this.inMove = true;

      document.getElementsByClassName('section')[id].scrollIntoView({behavior: 'smooth'});

      setTimeout(() => {
        this.inMove = false;
        if(!this.isMusicPlay) {
          const x = document.getElementById("audio");
          x.play()
        }
      }, 400);

    },
    touchStart(e) {
      if(!findElementByClass(e.path, 'dont-prevent')) e.preventDefault();
      this.touchStartY = e.touches[0].clientY;
    },
    touchMove(e) {
      if(this.inMove) return false;
      if(!findElementByClass(e.path, 'dont-prevent')) e.preventDefault();

      const currentY = e.touches[0].clientY;

      if(this.touchStartY < currentY) {
        this.moveDown();
      } else {
        this.moveUp();
      }

      this.touchStartY = 0;
      return false;
    },
    scrollHandler(e){
      var st = window.pageYOffset || document.documentElement.scrollTop; // Credits: "https://github.com/qeremy/so/blob/master/so.dom.js#L426"
      if (st > this.lastScrollTop){
          this.moveDown();
      } else {
          this.moveUp();
      }
      this.lastScrollTop = st <= 0 ? 0 : st;
    }
  },
  mounted(){
    const x = document.getElementById("audio");
    x.pause()
    this.calculateSectionOffsets();
  },
  created() {
    window.addEventListener('DOMMouseScroll', this.handleMouseWheelDOM);  // Mozilla Firefox
    window.addEventListener('mousewheel', this.handleMouseWheel, { passive: false }); // Other browsers

    window.addEventListener('touchstart', this.touchStart, { passive: false }); // mobile devices
    window.addEventListener('touchmove', this.touchMove, { passive: false }); // mobile devices
  },
  destroyed() {
    window.removeEventListener('mousewheel', this.handleMouseWheel, { passive: false });  // Other browsers
    window.removeEventListener('DOMMouseScroll', this.handleMouseWheelDOM); // Mozilla Firefox

    window.removeEventListener('touchstart', this.touchStart); // mobile devices
    window.removeEventListener('touchmove', this.touchMove); // mobile devices
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
