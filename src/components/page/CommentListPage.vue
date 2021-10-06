<template>
  <div class="flex outer-container p-6">
    <div id="comments-box" class="container inner-container my-6 mx-auto rounded-lg p-3 lg:p-5 max-h-screen overflow-auto">
      <ul>
        <li v-for="comment of comments" v-bind:key="comment" class="section">
          <Comment :author="comment.author" :comment="comment.comment"/>
        </li>
      </ul>
      <div>
        <button v-if="notViewAll" class="px-6 py-2 text-white rounded-full mb-5 mt-5 dont-prevent section" type="button" @click="viewAll">
          Show more comments
        </button>
      </div>
      <div v-if="loading" class="m-auto">
        <img src="/src/assets/images/loading-bar.gif" alt="" class="object-contain m-auto">
      </div>
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

      ],
      loading: false,
      notViewAll: true,
    }
  },
  mounted() {
  },
  updated(){
  },
  beforeCreate() {
    fetch('https://v1.nocodeapi.com/pandhuha/google_sheets/OVTrVJpdFULXGRwl?tabId=Displayed')
      .then((res) => res.json())
      .then(data => {
        const reversed = data.data.reverse()
        this.comments = (reversed.slice(0,3))
      })
      .catch(err => console.log(err))
  },
  methods: {
    viewAll(event){
      this.loading = true
      fetch('https://v1.nocodeapi.com/pandhuha/google_sheets/OVTrVJpdFULXGRwl?tabId=Displayed')
        .then((res) => res.json())
        .then(data => {
          this.comments = (data.data.reverse())
          this.loading = false
          this.notViewAll = false
        })
        .catch(err => console.log(err))
    }
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

button {
  background-color: #fff;
  color: #69765C;
  border-color: #69765C;
  border-width: 1pt;
  font-weight: bold;
}
</style>
