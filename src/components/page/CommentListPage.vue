<template>
  <div class="flex outer-container p-6">
    <div class="container inner-container my-6 mx-auto rounded-lg">
      <ul>
        <li v-for="comment of comments" v-bind:key="comment">
          <Comment :author="comment.name" :comment="comment.comment"/>
        </li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'
import Comment from '../Comment.vue'

const state = reactive({ count: 0 })
const comments = [
  {
    "name": "Lee Ikjoon",
    "comment": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eget neque auctor, facilisis enim in, tristique elit. Phasellus diam erat, bibendum eu dui rhoncus, condimentum venenatis nulla. Nulla a justo libero. Maecenas eget bibendum felis, eu lobortis ex."
  },
  {
    "name": "Kim Junwan",
    "comment": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eget neque auctor, facilisis enim in, tristique elit. Phasellus diam erat, bibendum eu dui rhoncus, condimentum venenatis nulla. Nulla a justo libero. Maecenas eget bibendum felis, eu lobortis ex."
  },
  {
    "name": "Seok Hyeong",
    "comment": "Lorem ipsum dolor sit amet, consectetur adipiscing elit. In eget neque auctor, facilisis enim in, tristique elit. Phasellus diam erat, bibendum eu dui rhoncus, condimentum venenatis nulla. Nulla a justo libero. Maecenas eget bibendum felis, eu lobortis ex."
  }
]

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
