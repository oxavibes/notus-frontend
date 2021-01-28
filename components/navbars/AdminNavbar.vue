<template>
  <!-- Navbar -->
  <nav
    class="absolute top-0 left-0 w-full z-10 bg-transparent md:flex-row md:flex-no-wrap md:justify-start flex items-center p-4 border-none md:border-b md:border-solid"
  >
    <div
      class="w-full mx-auto items-center flex justify-between md:flex-no-wrap flex-wrap md:px-10 px-4"
    >
      <!-- Brand -->
      <NuxtLink
        class="md:block text-left md:pb-2 text-gray-800 mr-0 inline-block whitespace-no-wrap lg:text-lg uppercase font-bold p-4 px-0"
        to="/"
      >
        Notus
      </NuxtLink>

      <!-- Form -->
      <form class="md:flex w-6/12 lg:w-5/12 flex-row flex-wrap items-center">
        <div class="relative flex w-full flex-wrap items-stretch">
          <!-- <span
            class="z-10 h-full leading-snug font-normal text-center text-gray-600 absolute bg-transparent rounded text-base items-center justify-center w-8 pl-3 py-3"
          >
            <i class="fas fa-search"></i>
          </span> -->
          <input
            type="text"
            placeholder="Search here..."
            class="px-3 py-3 placeholder-gray-700 text-gray-700 relative bg-white rounded text-xs shadow outline-none focus:outline-none focus:shadow-outline w-full pl-10"
          />
        </div>
      </form>

      <!-- User -->
      <ul class="list-none md:flex flex-col md:flex-row items-center">
        <user-dropdown />
      </ul>
    </div>
  </nav>
  <!-- End Navbar -->
</template>

<script>
import UserDropdown from '@/components/dropdowns/UserDropdown.vue'

export default {
  name: 'AdminNavbar',
  components: {
    UserDropdown,
  },
}
</script>
