<template>
  <div class="mb-2 px-2 w-full md:w-6/12 xl:w-3/12">
    <div class="shadow-md my-2 px-6 py-8 bg-white rounded">
      <span class="text-xs text-gray-500 text-bold block mb-2"
        >23 June, 2017</span
      >
      <router-link v-slot="{ href, navigate, isActive }" to="#">
        <a
          :href="href"
          class="text-sm md:text-md capitalize font-bold block mb-2"
          :class="[isActive ? 'text-green-500' : 'text-gray-800']"
          @click="navigate"
        >
          <span
            class="w-3 h-3 rounded-full bg-yellow-500 inline-block mr-1"
          ></span>
          The monkey-rope
        </a>
      </router-link>
      <p class="text-sm text-left text-gray-600">
        Being the savage's bowsman, thats is the person who pulled the bow-oar.
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardNote',
}
</script>
