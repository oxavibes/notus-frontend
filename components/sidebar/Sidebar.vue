<template>
  <nav
    class="md:left-0 md:block md:fixed md:top-0 md:bottom-0 md:overflow-y-auto md:flex-row md:flex-no-wrap md:overflow-hidden shadow-xl flex flex-wrap items-center justify-between relative md:w-64 z-10 py-4 px-6"
  >
    <div
      class="md:flex-col md:items-stretch md:min-h-full md:flex-no-wrap px-0 flex flex-wrap items-center justify-between w-full mx-auto"
    >
      <!-- Toggler -->
      <button
        class="cursor-pointer text-black opacity-50 md:hidden px-3 py-1 text-xl leading-none bg-transparent rounded border border-solid border-transparent"
        type="button"
        @click="toggleCollapseShow('bg-white m-2 py-3 px-6')"
      >
        <i class="fas fa-bars"></i>
      </button>

      <!-- Brand -->
      <router-link
        class="md:block text-left md:pb-2 text-gray-800 mr-0 inline-block whitespace-no-wrap lg:text-lg uppercase font-bold p-4 px-0"
        to="/"
      >
        Vue Notus
      </router-link>

      <!-- User -->
      <ul class="md:hidden items-center flex flex-wrap list-none">
        <li class="inline-block relative">
          <notification-dropdown />
        </li>
        <li class="inline-block relative">
          <user-dropdown />
        </li>
      </ul>

      <!-- Collapse -->
      <div
        class="md:flex md:flex-col md:items-stretch md:opacity-100 md:relative md:mt-4 md:shadow-none shadow absolute top-0 left-0 right-0 z-40 overflow-y-auto overflow-x-hidden h-auto items-center flex-1 rounded"
        :class="collapseShow"
      >
        <!-- Collapse header -->
        <div
          class="md:min-w-full md:hidden block pb-4 mb-4 border-b border-solid border-gray-300"
        >
          <div class="flex flex-wrap">
            <div class="w-6/12">
              <router-link
                class="md:block text-left md:pb-2 text-gray-700 mr-0 inline-block whitespace-no-wrap text-sm uppercase font-bold p-4 px-0"
                to="/"
              >
                Vue Notus
              </router-link>
            </div>
            <div class="w-6/12 flex justify-end">
              <button
                type="button"
                class="cursor-pointer text-black opacity-50 md:hidden px-3 py-1 text-xl leading-none bg-transparent rounded border border-solid border-transparent"
                @click="toggleCollapseShow('hidden')"
              >
                <i class="fas fa-times"></i>
              </button>
            </div>
          </div>
        </div>

        <!-- Form -->
        <form class="mt-6 mb-4 md:hidden">
          <div class="mb-3 pt-0">
            <input
              type="text"
              placeholder="Search"
              class="px-3 py-2 h-12 border border-solid border-gray-600 placeholder-gray-400 text-gray-700 bg-white rounded text-base leading-snug shadow-none outline-none focus:outline-none w-full font-normal"
            />
          </div>
        </form>

        <!-- Navigation -->
        <ul class="md:flex-col md:min-w-full flex flex-col list-none">
          <li class="items-center">
            <router-link
              v-slot="{ href, navigate, isActive }"
              to="/admin/dashboard"
            >
              <a
                class="text-xs capitalize py-3 font-bold block font-mono"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
                :href="href"
                @click="navigate"
              >
                <i
                  class="fas fa-tv fa-fw fa-lg mr-3"
                  :class="[isActive ? 'opacity-75' : 'text-gray-800']"
                ></i>
                Overview
              </a>
            </router-link>
          </li>

          <li class="items-center">
            <router-link
              v-slot="{ href, navigate, isActive }"
              to="/admin/tables"
            >
              <a
                class="text-xs capitalize py-3 font-bold block"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
                :href="href"
                @click="navigate"
              >
                <i
                  class="fas fa-tag fa-fw fa-lg mr-3"
                  :class="[isActive ? 'opacity-75' : 'text-gray-800']"
                ></i>
                Starred
              </a>
            </router-link>
          </li>

          <!-- <li class="items-center">
            <router-link to="/admin/maps" v-slot="{ href, navigate, isActive }">
              <a
                :href="href"
                @click="navigate"
                class="text-xs capitalize py-3 font-bold block"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
              >
                <i
                  class="fas fa-sticky-note fa-fw fa-lg mr-3"
                  :class="[isActive ? 'opacity-75' : 'text-gray-800']"
                ></i>
                Notes
              </a>
            </router-link>
          </li> -->

          <!-- <li class="items-center">
            <router-link to="/admin/maps" v-slot="{ href, navigate, isActive }">
              <a
                :href="href"
                @click="navigate"
                class="text-xs capitalize py-3 font-bold block"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
              >
                <i
                  class="fas fa-map-marked fa-fw fa-lg mr-3"
                  :class="[isActive ? 'opacity-75' : 'text-gray-800']"
                ></i>
                Output
              </a>
            </router-link>
          </li> -->

          <!-- <li class="items-center">
            <router-link to="/admin/maps" v-slot="{ href, navigate, isActive }">
              <a
                :href="href"
                @click="navigate"
                class="text-xs capitalize py-3 font-bold block"
                :class="[isActive ? 'text-green-500' : 'text-gray-700']"
              >
                <i
                  class="fas fa-headphones fa-fw fa-lg mr-3"
                  :class="[
                    isActive ? 'opacity-75 text-green-500' : 'text-gray-700',
                  ]"
                ></i>
                Support
              </a>
            </router-link>
          </li> -->
        </ul>

        <!-- Divider -->
        <hr class="my-4 md:min-w-full" />

        <h6
          class="md:min-w-full text-gray-700 text-sm font-semibold block pt-1 pb-2 no-underline"
        >
          Categories
        </h6>

        <!-- Navigation -->

        <ul class="md:flex-col md:min-w-full flex flex-col list-none md:mb-4">
          <li class="items-center">
            <router-link v-slot="{ href, navigate, isActive }" to="/admin/maps">
              <a
                class="text-xs capitalize py-3 font-semibold inline-flex items-center"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
                :href="href"
                @click="navigate"
              >
                <span
                  class="w-3 h-3 rounded-full ml-3 mr-3 bg-yellow-500 block"
                ></span>

                Projects
              </a>
            </router-link>
          </li>

          <li class="items-center">
            <router-link v-slot="{ href, navigate, isActive }" to="/admin/maps">
              <a
                class="text-xs capitalize py-3 font-semibold inline-flex items-center"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
                :href="href"
                @click="navigate"
              >
                <span
                  class="w-3 h-3 rounded-full ml-3 mr-3 bg-red-500 block"
                ></span>

                Business
              </a>
            </router-link>
          </li>

          <li class="items-center">
            <router-link v-slot="{ href, navigate, isActive }" to="/admin/maps">
              <a
                class="text-xs capitalize py-3 font-semibold inline-flex items-center"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
                :href="href"
                @click="navigate"
              >
                <span
                  class="w-3 h-3 rounded-full ml-3 mr-3 bg-blue-400 block"
                ></span>

                Personal
              </a>
            </router-link>
          </li>

          <!-- <li class="items-center">
            <router-link to="/admin/maps" v-slot="{ href, navigate, isActive }">
              <a
                :href="href"
                @click="navigate"
                class="text-xs capitalize py-3 font-semibold inline-flex items-center"
                :class="[isActive ? 'text-green-500' : 'text-gray-800']"
              >
                <i
                  class="fas fa-plus fa-fw fa-lg ml-2 mr-2"
                  :class="[
                    isActive ? 'opacity-75 text-green-500' : 'text-gray-700',
                  ]"
                ></i>

                Add New
              </a>
            </router-link>
          </li> -->
        </ul>
      </div>
    </div>
  </nav>
</template>
); }

<script>
import UserDropdown from '~/components/dropdowns/UserDropdown.vue'
import NotificationDropdown from '~/components/dropdowns/NotificationDropdown.vue'

export default {
  components: {
    NotificationDropdown,
    UserDropdown,
  },
  data() {
    return {
      collapseShow: 'hidden',
    }
  },
  methods: {
    toggleCollapseShow(classes) {
      this.collapseShow = classes
    },
  },
}
</script>
