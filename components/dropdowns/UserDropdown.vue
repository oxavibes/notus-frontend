<template>
  <div>
    <a
      ref="btnDropdownRef"
      class="text-gray-600 block"
      href="#pablo"
      @click="toggleDropdown($event)"
    >
      <div class="items-center flex">
        <span
          class="w-12 h-12 text-sm text-white bg-gray-300 inline-flex items-center justify-center rounded-full"
        >
          <img
            alt="User Profile Image"
            class="w-full rounded-full align-middle border-none shadow-lg"
            :src="image"
          />
        </span>
      </div>
    </a>
    <div
      ref="popoverDropdownRef"
      class="bg-white text-base z-50 float-left py-2 list-none text-center rounded shadow-lg min-w-48 divide-y"
      :class="{
        hidden: !dropdownPopoverShow,
        block: dropdownPopoverShow,
      }"
    >
      <router-link v-slot="{ href }" to="/admin/settings">
        <a
          :href="href"
          class="text-sm py-2 px-4 font-normal block w-full whitespace-no-wrap bg-transparent text-gray-800"
          @click="hidePopover"
        >
          Settings
        </a>
      </router-link>
      <a
        href="#"
        class="text-sm py-2 px-4 block w-full whitespace-no-wrap bg-transparent font-bold text-gray-800"
      >
        Logout
      </a>
    </div>
  </div>
</template>

<script>
import { createPopper } from '@popperjs/core'

import image from '~/assets/img/team-1-800x800.jpg'

export default {
  name: 'UserDropdown',
  data() {
    return {
      dropdownPopoverShow: false,
      image,
    }
  },
  methods: {
    toggleDropdown(event) {
      event.preventDefault()
      if (this.dropdownPopoverShow) {
        this.dropdownPopoverShow = false
      } else {
        this.dropdownPopoverShow = true
        createPopper(this.$refs.btnDropdownRef, this.$refs.popoverDropdownRef, {
          placement: 'bottom',
        })
      }
    },
    hidePopover() {
      this.dropdownPopoverShow = false
    },
  },
}
</script>
