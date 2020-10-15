<template>
  <div id="app">
    <WelcomeMessage />
    <Courses />
    <FAQ />
  </div>
</template>

<script lang="ts">
import Courses from '@/views/Courses.vue'
import FAQ from '@/views/FAQ.vue'
import WelcomeMessage from '@/views/WelcomeMessage.vue'

export default {
  name: 'App',
  components: {
    Courses,
    FAQ,
    WelcomeMessage
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
