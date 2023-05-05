<template>
  <section class="max-w-7xl mx-auto p-5 my-20">

    <h1 class="flex justify-center text-2xl">Data Bulanan </h1>

    <div v-if="pending">
      Loading ...
    </div>
    <div v-else>

      <div v-for="schedule in monthly.prayerTime">
        <ul role="list" class="divide-y divide-gray-100 overflow-hidden shadow-sm ring-1 ring-gray-900/5 sm:rounded-xl">
          <li class="relative gap-x-6 px-4 py-5 hover:bg-gray-50 sm:px-6">


            <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-8">
              <div class="text-sm font-semibold leading-6 ">
                {{ schedule.date }}
                <br>
                {{ schedule.hijri }}

              </div>
              <div class="prayer-time"> {{ schedule.imsak }} </div>
              <div class="prayer-time"> {{ schedule.fajr }} </div>
              <div class="prayer-time"> {{ schedule.syuruk }} </div>
              <div class="prayer-time"> {{ schedule.dhuhr }} </div>
              <div class="prayer-time"> {{ schedule.asr }} </div>
              <div class="prayer-time"> {{ schedule.maghrib }} </div>
              <div class="prayer-time"> {{ schedule.isha }} </div>
            </div>

          </li>
        </ul>
      </div>

    </div>

  </section>
</template>

<script setup>
const { pending, data: monthly } = useLazyFetch('https://solat.my/api/monthly/sgr01')
</script>
