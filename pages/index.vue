<template>
  <div class="flex">

    <section class="flex mx-auto max-w-7xl p-5 justify-center w-full h-screen items-center ">

      <!-- you will need to handle a loading state -->
      <div class="loading" v-if="pending">
        <h4> Loading ... </h4>
      </div>
      <div class="w-full" v-else>
        <!-- <div class="text-center">
            <h1 class="text-thin">{{ zone }} {{ location }}</h1>
          </div>
        -->
        <div class="flex justify-between">
          <h3 class="text-4xl">{{ daily.prayerTime[0].date }}</h3>
          <h3 class="text-4xl">{{ daily.prayerTime[0].hijri }}</h3>4
        </div>
        <br>
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-7">
          <div class="flex flex-col items-center">
            <img src="/images/subuh.svg" width="96" height="96" />
            <h3>Imsak</h3>
            <h4 class="text-thin">{{ daily.prayerTime[0].imsak }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/subuh.svg" width="96" height="96" />
            <h3>Subuh</h3>
            <h4 class="text-thin"> {{ daily.prayerTime[0].fajr }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/dhuha.svg" width="96" height="96" />
            <h3>Syuruk</h3>
            <h4 class="text-thin"> {{ daily.prayerTime[0].syuruk }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/zohor.svg" width="96" height="96" />
            <h3>Zohor</h3>
            <h4 class="text-thin"> {{ daily.prayerTime[0].dhuhr }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/asar.svg" width="96" height="96" />
            <h3>Asar</h3>
            <h4 class="text-thin">{{ daily.prayerTime[0].asr }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/maghrib.svg" width="96" height="96" />
            <h3>Maghrib</h3>
            <h4 class="text-thin">{{ daily.prayerTime[0].maghrib }}</h4>
          </div>
          <div class="flex flex-col items-center">
            <img src="/images/isyak.svg" width="96" height="96" />
            <h3>Isyak</h3>
            <h4 class="text-thin">{{ daily.prayerTime[0].isha }}</h4>
          </div>
        </div>
        <div class="flex justify-center">
          <libraryButtonNuxt value="Bulanan" to='/monthly' class="m-2" />
        </div>

      </div>

    </section>
  </div>
</template>

<script setup>
const { pending, data: daily } = useLazyFetch('https://solat.my/api/daily/sgr01')
</script>
