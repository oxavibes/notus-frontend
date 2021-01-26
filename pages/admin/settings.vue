<template>
  <div class="flex flex-wrap">
    <div class="w-full px-4">
      <CardSettings />
    </div>
  </div>
</template>
<script>
import CardSettings from '@/components/cards/CardSettings.vue'

export default {
  components: {
    CardSettings,
  },
  layout: 'Admin',
}
</script>
