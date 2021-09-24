<template>
  <div class="section flex outer-container p-6">
    <div class="container inner-container my-6 mx-auto rounded-lg p-3 md:p-5">
      <ul>
        <li v-for="comment of comments" v-bind:key="comment">
          <Comment :author="comment.author" :comment="comment.comment"/>
        </li>
      </ul>
      <div>
        <button v-if="notViewAll" class="px-6 py-2 text-white rounded-full mb-5 mt-5" type="button" @click="viewAll">
          Lihat Semua
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
      notViewAll: true
    }
  },
  mounted() {
    fetch('https://v1.nocodeapi.com/pandhuha/google_sheets/OVTrVJpdFULXGRwl?tabId=Displayed')
      .then((res) => res.json())
      .then(data => this.comments = (data.data.slice(-3)))
      .catch(err => console.log(err))
  },
  methods: {
    viewAll(event){
      this.loading = true
      fetch('https://v1.nocodeapi.com/pandhuha/google_sheets/OVTrVJpdFULXGRwl?tabId=Displayed')
        .then((res) => res.json())
        .then(data => {
          this.comments = (data.data)
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
  background-color: #69765C;
  font-weight: bold;
}
</style>
