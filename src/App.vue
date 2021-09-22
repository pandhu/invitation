<template>
  <FrontPage />
  <QuranVersePage />
  <BrideGroomPage />
  <DetailsPage />
  <MapsPage />
  <CommentPage />
  <CommentListPage />
  <FooterPage />
</template>

<script setup>
import FrontPage from './components/page/FrontPage.vue'
import QuranVersePage from './components/page/QuranVersePage.vue'
import BrideGroomPage from './components/page/BrideGroomPage.vue'
import DetailsPage from './components/page/DetailsPage.vue'
import MapsPage from './components/page/MapsPage.vue'
import CommentPage from './components/page/CommentPage.vue'
import CommentListPage from './components/page/CommentListPage.vue'
import FooterPage from './components/page/FooterPage.vue'

// This starter template is using Vue 3 experimental <script setup> SFCs
// Check out https://github.com/vuejs/rfcs/blob/master/active-rfcs/0040-script-setup.md
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
