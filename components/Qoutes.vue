<template>
  <div>
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div
        class="
          relative
          py-24
          px-8
          bg-transparent
          rounded-xl
          overflow-hidden
          lg:px-16 lg:grid lg:grid-cols-2 lg:gap-x-8
        "
      >
        <div
          class="
            absolute
            inset-0
            opacity-50
            filter
            saturate-0
            mix-blend-multiply
          "
        >
          <img
            :src="url + qoute.content"
            alt=""
            class="w-full h-full object-cover"
          />
        </div>
        <div class="relative lg:col-span-1">
          <blockquote class="mt-6 text-white">
            <p class="text-xl font-medium sm:text-2xl italic">
              "{{ qoute.content }}"
            </p>
            <template v-if="qoute.author">
              <footer class="mt-6">
                <p class="flex flex-col font-medium">
                  <span>- {{ qoute.author }}</span>
                </p>
              </footer>
            </template>
          </blockquote>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  props: ['qoute', 'img'],
  data() {
    return {
      url: 'https://source.unsplash.com/random/?nature,',
    }
  },
}
</script>
