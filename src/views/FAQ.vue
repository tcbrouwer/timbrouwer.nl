<template>
  <div>
    <h1>Veelgestelde vragen</h1>
    <hr>
    <div v-for="aq in faq" :key="aq.a">
      <p>
        Q: {{ aq.q }}
      </p>
      <p>
          A: {{ aq.a }}
      </p>
      <hr>
      </div>
  </div>
</template>

<script lang="ts">
import faq from '@/content/faq.json'

export default {
  name: 'FAQ',
  data() {
    return {
      faq: []
    }
  },
  mounted() {
    this.getFAQ()
  },
  methods: {
    getFAQ() {
      // Should get from server
      this.faq = faq 
    }
  }
}
</script>

<style scoped>
</style>