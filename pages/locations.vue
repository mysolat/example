<template>
  <section class="max-w-7xl mx-auto p-5 mt-20">

    <h1 class="flex justify-center text-2xl">
      Locations
    </h1>

    <div v-if="pending">
      Loading ...
    </div>
    <div v-else>
      <div v-for="location in locations">
        <ul role="list" class="divide-y divide-gray-100 overflow-hidden shadow-sm ring-1 ring-gray-900/5 sm:rounded-xl">
          <li class="relative flex justify-between gap-x-6 px-4 py-5 hover:bg-gray-50 sm:px-6">
            <div class="flex gap-x-4">
              <div class="min-w-0 flex-auto">
                <p class="text-sm font-semibold leading-6 ">
                  {{ location.state }} {{ location.code }}
                  <NuxtLink to="/">
                    {{ location.location }}
                  </NuxtLink>
                </p>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>

  </section>
</template>

<script setup>
const { pending, data: locations } = useLazyFetch('https://solat.my/api/locations')
</script>
