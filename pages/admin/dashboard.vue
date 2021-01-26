<template>
  <div>
    <div class="w-full">
      <button class="w-10 h-10 bg-yellow-500 rounded-full focus:outline-none">
        <i
          class="fas fa-plus fa-lg"
          :class="[isActive ? 'opacity-75' : 'text-white']"
        ></i>
      </button>
    </div>
    <div class="flex flex-wrap -mx-2 overflow-hidden">
      <card-note v-for="i in 12" :key="i"></card-note>
    </div>
    <div class="flex flex-wrap mt-4">
      <div class="w-full xl:w-8/12 mb-12 xl:mb-0 px-4">
        <!-- <card-page-visits /> -->
      </div>
      <div class="w-full xl:w-4/12 px-4">
        <!-- <card-social-traffic /> -->
      </div>
    </div>
  </div>
</template>
<script>
import CardNote from '@/components/cards/CardNote.vue'
export default {
  components: {
    CardNote,
  },
  layout: 'Admin',
  data() {
    return {
      isActive: false,
    }
  },
}
</script>
