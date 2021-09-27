<template>
  <div class="py-3 container px-3">
    <div v-if="!isFinish" class="flex justify-center md:flex-row flex-col">
        <div class="border-2 mx-3 p-5 md:p-10 md:mx-5 mb-5">
          <p class="md:text-6xl text-xl">{{days}}</p>
          <p>days</p>
        </div>
        <div class="border-2 mx-3 p-5 md:p-10 md:mx-5 mb-5">
          <p class="md:text-6xl text-xl">{{hours}}</p>
          <p>hours</p>
        </div>
        <div class="border-2 mx-3 p-5 md:p-10 md:mx-5 mb-5">
          <p class="md:text-6xl text-xl">{{minutes}}</p>
          <p>minutes</p>
        </div>
        <div class="border-2 mx-3 p-5 md:p-10 md:mx-5 mb-5">
          <p class="md:text-6xl text-xl">{{seconds}}</p>
          <p>seconds</p>
        </div>
    </div>
    <div v-if="isFinish"><p>We are Married</p></div>
  </div>
</template>

<script setup>
import { defineProps, reactive } from 'vue'

const props = defineProps({
  datetime: String,
})

</script>

<script>
export default {
  data() {
    return {
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0,
      isFinish: false,
    }
  },
  methods: {
    setCountDown() {

      var now = new Date().getTime();
      var countDownDate = new Date(this.datetime).getTime();
      var distance = countDownDate - now;

      // Time calculations for days, hours, minutes and seconds
      this.days = pad(Math.floor(distance / (1000 * 60 * 60 * 24)), 2);
      this.hours = pad(Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)), 2);
      this.minutes = pad(Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)), 2);
      this.seconds = pad(Math.floor((distance % (1000 * 60)) / 1000), 2);

      // If the count down is finished, write some text
      if (distance < 0) {
        this.isFinish = true
      }
    },
    initialize() {
      var now = new Date().getTime();
      var countDownDate = new Date(this.datetime).getTime();
      var distance = countDownDate - now;

      // Time calculations for days, hours, minutes and seconds
      this.days = pad(Math.floor(distance / (1000 * 60 * 60 * 24)), 2);
      this.hours = pad(Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)), 2);
      this.minutes = pad(Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60)), 2);
      this.seconds = pad(Math.floor((distance % (1000 * 60)) / 1000), 2);
    }
  },
  created() {
    this.initialize()
    setInterval(this.setCountDown, 1000)
  }
}

function pad (str, max) {
  str = str.toString();
  return str.length < max ? pad("0" + str, max) : str;
}
</script>

<style scoped>

@font-face {
  font-family: "Trajan Pro";
  src: url('../src/assets/fonts/TrajanPro-Bold.otf');
}

p {
  font-family: "Trajan Pro";
  color: #69765C  ;
}

</style>
