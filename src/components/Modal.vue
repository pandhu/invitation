<template>
  <div>
    <div class="calendar-button my-8 md:my-16" v-on:click="toggleModal()">
      <a class="p-3 px-3 md:p-3 md:px-10 rounded dont-prevent">ADD TO YOUR CALENDAR</a>
    </div>
    <div v-if="showModal" class="overflow-x-hidden overflow-y-auto fixed inset-0 z-50 outline-none focus:outline-none justify-center items-center flex dont-prevent m-10 md:m-auto">
      <div class="relative w-auto my-6 mx-auto max-w-3xl">
        <!--content-->
        <div class="border-0 rounded-lg shadow-lg relative flex flex-col w-full bg-white outline-none focus:outline-none">
          <!--header-->
          <div class="flex items-start justify-between p-5 border-b border-solid border-blueGray-200 rounded-t">
            <h3 class="text-md md:text-3xl font-semibold">
              Please choose your calendar
            </h3>
            <button class="p-1 ml-auto bg-transparent border-0 text-black opacity-5 float-right text-3xl leading-none font-semibold outline-none focus:outline-none" v-on:click="toggleModal()">
              <span class="bg-transparent text-black opacity-5 h-6 w-6 text-2xl block outline-none focus:outline-none">
                ×
              </span>
            </button>
          </div>
          <!--body-->
          <div class="relative p-6 flex justify-center">
            <div class="calendar-inner-button mx-5 "><a href="https://calendar.google.com/event?action=TEMPLATE&tmeid=NzRsYWluZWJpNWM1YmtnMjlyams2Y2pkbTAgaW5uZ3NuNmFiMDNxZ2I1YTk5YWVqaDEzMDBAZw&tmsrc=inngsn6ab03qgb5a99aejh1300%40group.calendar.google.com" target="_blank" class="p-3 px-3 md:p-3 md:px-10 rounded">Google</a></div>
            <div class="calendar-inner-button mx-5"><a href="/src/assets/nilam-pandhu.ics" class="p-3 px-3 md:p-3 md:px-10 rounded">Apple</a></div>
          </div>
          <!--footer-->
          <div class="flex items-center justify-end md:p-6 p-3 border-t border-solid border-blueGray-200 rounded-b">
            <button class="text-red-500 bg-transparent border border-solid border-red-500 hover:bg-red-500 hover:text-white active:bg-red-600 font-bold uppercase text-sm px-6 md:py-3 py-2 rounded outline-none focus:outline-none mr-1 mb-1 ease-linear transition-all duration-150" type="button" v-on:click="toggleModal()">
              Close
            </button>
          </div>
        </div>
      </div>
    </div>
    <div v-if="showModal" class="opacity-25 fixed inset-0 z-40 bg-black"></div>
  </div>
</template>

<script>
export default {
  name: "regular-modal",
  data() {
    return {
      showModal: false
    }
  },
  methods: {
    toggleModal: function(){
      this.showModal = !this.showModal;
    }
  }
}
</script>
<style scoped>
.calendar-button > a{
  font-family: "Open Sans";
  color:#69765C;
  font-weight: bold;
  background-color: white;
}

.calendar-inner-button > a{
  font-family: "Open Sans";
  color:white;
  font-weight: bold;
  background-color: #69765C;
}
</style>
