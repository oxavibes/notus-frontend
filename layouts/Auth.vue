<template>
  <div>
    <auth-navbar />
    <main>
      <section class="relative w-full h-full py-40 min-h-screen">
        <div
          class="absolute top-0 w-full h-full bg-gray-900 bg-no-repeat bg-full"
          :style="`background-image: url('${registerBg2}');`"
        ></div>
        <Nuxt />
        <footer-small absolute />
      </section>
    </main>
  </div>
</template>
<script>
import AuthNavbar from '~/components/navbars/AuthNavbar.vue'
import FooterSmall from '~/components/footers/FooterSmall.vue'
import registerBg2 from '~/assets/img/register_bg_2.png'

export default {
  components: {
    AuthNavbar,
    FooterSmall,
  },
  data() {
    return {
      registerBg2,
    }
  },
}
</script>
