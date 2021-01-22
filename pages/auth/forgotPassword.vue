<template>
  <div class="container mx-auto px-4 h-full">
    <div class="flex content-center items-center justify-center h-full">
      <div class="w-full md:w-6/12 lg:w-4/12 px-4">
        <div
          class="relative flex flex-col min-w-0 break-words w-full mb-6 shadow-lg rounded-lg bg-gray-300 border-0"
        >
          <div class="flex-auto px-4 lg:px-10 py-6">
            <div class="text-gray-600 text-center mb-3 font-bold">
              <small>Password recovery</small>
            </div>
            <form>
              <div class="relative w-full mb-3">
                <label
                  class="block uppercase text-gray-700 text-xs font-bold mb-2"
                  htmlFor="grid-password"
                >
                  Email
                </label>
                <input
                  type="email"
                  class="px-3 py-3 placeholder-gray-400 text-gray-700 bg-white rounded text-sm shadow focus:outline-none focus:shadow-outline w-full ease-linear transition-all duration-150"
                  placeholder="youremail@mail.com"
                />
              </div>

              <div class="text-center mt-6">
                <button
                  class="bg-gray-900 text-white active:bg-gray-700 text-sm font-bold uppercase px-6 py-3 rounded shadow hover:shadow-lg outline-none focus:outline-none mr-1 mb-1 w-full ease-linear transition-all duration-150"
                  type="button"
                >
                  Recover
                </button>
              </div>

              <hr class="mt-6 border-b-1 border-gray-400" />

              <div class="flex flex-wrap mt-6 relative justify-around">
                <div class="w-auto">
                  <NuxtLink to="/auth">
                    <small class="text-sm capitalize font-bold">Login</small>
                  </NuxtLink>
                </div>
                <div class="w-auto text-right">
                  <NuxtLink to="/auth/register">
                    <small class="text-sm capitalize font-bold">
                      Sign up
                    </small>
                  </NuxtLink>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import github from '~/assets/img/github.svg'
import google from '~/assets/img/google.svg'

export default {
  layout: 'Auth',
  data() {
    return {
      github,
      google,
    }
  },
}
</script>
