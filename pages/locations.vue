<template>
  <section class="max-w-7xl mx-auto p-5 mt-20">

    <h1 class="flex justify-center text-2xl"> Pilih Lokasi </h1>

    <div v-if="pending">
      Loading ...
    </div>
    <div v-else>
      <div v-for="(state, index) in states" :key="index">
        <h1>{{ index }}</h1>
        <div v-for="location in state">
          <ul role="list" class="divide-y divide-gray-100 overflow-hidden shadow-sm ring-1 ring-gray-900/5 sm:rounded-xl">
            <li class="relative flex justify-between gap-x-6 px-4 py-5 hover:bg-gray-50 sm:px-6">
              <div class="flex gap-x-4">
                <div class="min-w-0 flex-auto">
                  <p class="text-sm font-semibold leading-6 ">

                    <NuxtLink to="/"> {{ location.code }} - {{ location.location }} </NuxtLink>
                  </p>
                </div>
              </div>
            </li>
          </ul>
        </div>

      </div>
    </div>

  </section>
</template>

<script setup>
const { pending, data: states } = useFetch('https://solat.my/api/locations', {
  onResponse({ request, response, options }) {

    var groupedData = {};
    response._data.forEach(item => {
      if (!groupedData[item.state]) {
        groupedData[item.state] = [];
      }
      groupedData[item.state].push(item);
    })
    return response._data = groupedData;
  }
})

</script>
