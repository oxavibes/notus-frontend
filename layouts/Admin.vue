<template>
  <div>
    <sidebar />
    <div class="relative md:ml-64">
      <admin-navbar />
      <!-- <header-stats /> -->
      <div class="px-4 md:px-10 mx-auto w-full pt-8 md:pt-24">
        <Nuxt />
        <footer-admin />
      </div>
    </div>
  </div>
</template>
<script>
import AdminNavbar from '~/components/navbars/AdminNavbar.vue'
import Sidebar from '~/components/sidebar/Sidebar.vue'
import FooterAdmin from '~/components/footers/FooterAdmin.vue'

export default {
  components: {
    AdminNavbar,
    Sidebar,
    FooterAdmin,
  },
}
</script>
