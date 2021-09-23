<template>
  <div class="flex outer-container p-6">
    <div class="container inner-container my-6 mx-auto rounded-lg">
      <ul>
        <li v-for="comment of comments" v-bind:key="comment">
          <Comment :author="comment.author" :comment="comment.comment"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'
import Comment from '../Comment.vue'

</script>

<script>
export default {
  data() {
    return {
      comments: [

      ]
    }
  },
  mounted() {
    fetch('https://v1.nocodeapi.com/pandhuha/google_sheets/OVTrVJpdFULXGRwl?tabId=Displayed')
    .then((res) => res.json())
    .then(data => this.comments = (data.data.slice(0, 3)))
    .catch(err => console.log(err))
  }
}
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

.outer-container {
  background-color: #f8f8f8;
}

.inner-container {
  background-color: #fff;
}
</style>
