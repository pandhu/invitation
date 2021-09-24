<template>
  <div class="py-3 container px-3 md:text-2xl">
    <div v-if="!isFinish"><p>{{days}} Hari {{hours}} Jam {{minutes}} Menit {{seconds}} Detik</p></div>
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
      this.days = Math.floor(distance / (1000 * 60 * 60 * 24));
      this.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      this.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      this.seconds = Math.floor((distance % (1000 * 60)) / 1000);

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
      this.days = Math.floor(distance / (1000 * 60 * 60 * 24));
      this.hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
      this.minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
      this.seconds = Math.floor((distance % (1000 * 60)) / 1000);
    }
  },
  created() {
    this.initialize()
    setInterval(this.setCountDown, 1000)
  }
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
