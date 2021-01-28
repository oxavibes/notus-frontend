<template>
  <div>
    <!-- <sidebar /> -->
    <div class="relative h-screen">
      <admin-navbar />
      <div class="px-4 pt-24 md:px-10 mx-auto w-full md:pt-8 md:pt-24">
        <Nuxt />
      </div>
    </div>
  </div>
</template>
<script>
import AdminNavbar from '@/components/navbars/AdminNavbar.vue'
// import Sidebar from '@/components/sidebar/Sidebar.vue'

export default {
  components: {
    AdminNavbar,
    // Sidebar,
  },
}
</script>
