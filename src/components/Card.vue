<template>
  <container class="flex items-center justify-center flex-wrap bg-blue-500 p-6 h-screen">
    <div class="flex items-center justify-center bg-gray-50 py-20 px-4 sm:px-6 lg:px-20">
      <div class="max-w-md w-full space-y-8">
        <form class="mt-8 space-y-8" action="#" method="POST">
          <div class=" w-80">
            <div class="">
              <span class="text-gray-500">Card Name</span>
              <input id="card-name" name="card-name" type="text" required
                class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-blue-500 focus:border-blue-500 focus:z-10 sm:text-sm">
            </div>
            <div class="pt-2">
              <span class="text-gray-500">Card Number</span>
              <input id="card-number" name="card-number" type="number" required
                class="appearance-none rounded-none relative block w-full px-3 py-2 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-blue-500 focus:border-blue-500 focus:z-10 sm:text-sm">
            </div>
            <div class="pt-2">
              <span class="text-gray-500">Expiration Date</span>
              <div class="flex">
                <label class="block">
                  <select v-model="expirationMonth" class="w-32 h-9 mt-1 mr-2 border">
                    <option value="" disabled>Month</option>
                    <option v-for="month in months" :key="month.id" :value="month.id">{{month}}</option>
                  </select>
                </label>
                <label class="block">
                  <select v-model="expirationYear" class="w-28 h-9 mt-1 mr-2 border">
                    <option value="" disabled>Year</option>
                    <option v-for="year in years" :key="year.id" :value="year.id">{{year}}</option>
                  </select>
                </label>
                <label>
                  <input id="cvv" v-model="cvv" name="cvv" type="text" required
                    class="appearance-none rounded-none relative block mt-1 h-9 w-16 border border-gray-300 placeholder-gray-500 text-gray-900 focus:outline-none focus:ring-blue-500 focus:border-blue-500 focus:z-10 sm:text-sm">
                </label>
              </div>
            </div>
          </div>
          <div>
            <button type="submit"
              class="group relative w-full flex justify-center py-2 px-4 border border-transparent text-sm font-medium rounded-md text-white bg-blue-600 hover:bg-blue-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-blue-500">
              <span class="absolute left-0 inset-y-0 flex items-center pl-3">
                <svg class="h-5 w-5 text-blue-500 group-hover:text-blue-400" xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                  <path fill-rule="evenodd"
                    d="M5 9V7a5 5 0 0110 0v2a2 2 0 012 2v5a2 2 0 01-2 2H5a2 2 0 01-2-2v-5a2 2 0 012-2zm8-2v2H7V7a3 3 0 016 0z"
                    clip-rule="evenodd" />
                </svg>
              </span>
              Submit
            </button>
          </div>
        </form>
      </div>
    </div>
  </container>
</template>

<script>
  export default {
    name: 'Card',
    data() {
      return {
        expirationMonth: '',
        expirationYear: '',
        cvv: '',
        months: [
          'January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October',
          'November', 'December'
        ],
        years: [
          2021, 2022, 2023, 2024, 2025, 2026, 2027, 2028, 2029, 2030
        ]
      }
    },
  }
</script>