<template>
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="max-w-3xl mx-auto pt-10">
      <qoutes :qoute="qoutes" :img="this.randomBgImg" />
      <div class="mt-36 flex justify-center mb-36">
        <button
          @click.prevent="randomQuote"
          class="text-xl text-gray-600 focus:outline-none"
        >
          next &#8250;
        </button>
      </div>
      <footer class="text-center text-gray-500">
        <a
          href="https://norjamillekasan.netlify.app"
          target="_blank"
          class="underline"
          >Developer</a
        >
      </footer>
    </div>
  </div>
</template>

<script>
import Qoutes from '../components/Qoutes.vue'
export default {
  components: {
    Qoutes,
  },
  data() {
    return {
      randomBgImg: '',
      tags: ['mountain', 'inspirational', 'nature', 'city', 'love'],
      randomTag: '',
      qoutes: '',
      picked: '',
    }
  },

  methods: {
    async randomQuote() {
      const response = await fetch('https://api.quotable.io/random')
      const data = await response.json()

      return (this.qoutes = data)
    },
  },
  mounted() {
    this.randomQuote()
  },
}
</script>

<style>
body {
  background-color: #eec9d2;
}
</style>
