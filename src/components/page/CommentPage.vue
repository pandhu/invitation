<template>
  <div class="flex my-10 py-10" :class="section">
    <div class="container m-auto">
      <div class="title-container mb-10">
        <a class="text-xl">Send your duas and wishes</a>
      </div>
      <div v-if="submitted" class="submitted mx-5 rounded p-5">
        <p class="text-white">Thanks for your duas and wishes</p>
      </div>
      <div v-if="failedSubmit" class="bg-red-300 mx-5 rounded p-5">
        <p class="text-white">Name and Message can't be blank</p>
      </div>
      <div class="form-container p-6 md:flex md:justify-center">
        <form class="w-full max-w-lg dont-prevent">
          <div class="flex flex-wrap mx-auto mb-6">
            <div class="w-full px-3 mb-6">
              <input class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 mb-3 leading-tight focus:outline-none focus:bg-white" type="text" placeholder="Name" v-model="author">
            </div>
            <div class="w-full px-3">
              <textarea class="appearance-none block w-full bg-gray-200 text-gray-700 border border-gray-200 rounded py-3 px-4 leading-tight focus:outline-none focus:bg-white h-36" type="text" placeholder="Message" v-model="comment"></textarea>
            </div>
          </div>
          <button class="px-6 py-2 text-white rounded-full" type="button" @click="submit">
            Send
          </button>
          <div v-if="submiting" class="m-auto">
            <img src="/src/assets/images/loading-bar.gif" alt="" class="object-contain m-auto">
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'
const section = isMobile() ? 'section' : ''

</script>

<script>
export default {
  data: () => ({
    author: '',
    comment: '',
    submitted: false,
    failedSubmit: false,
    submiting: false,
  }),
  methods: {
    submit(event) {
      this.submitted = false
      this.failedSubmit = false
      this.submiting = true

      const requestOptions = {
        method: "POST",
        headers: { "Content-Type": "application/json" },
        body: JSON.stringify({ "entry.1195869260": this.author, "entry.2060015970": this.comment })
      };

      if(this.author == '' || this.comments == '') {
        this.failedSubmit = true
        this.submiting = false

        return
      }

      fetch("https://restful-google-form.vercel.app/api/forms/1FAIpQLSf2dNR2Nz_yIMi59bZKLK-u3fJgMTnOwCeGRTgYHDQyBAIDkw", requestOptions)
        .then((res) => {
          this.submitted = true
          this.failedSubmit = false
          this.author = ''
          this.comment = ''
          this.submiting = false

        })
    }
  }
}

function isMobile() {
  if(/Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent)) {
     return true
   } else {
     return false
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

button {
  background-color: #69765C;
  font-weight: bold;
}

.submitted {
  background-color: #69765C;
}
</style>
