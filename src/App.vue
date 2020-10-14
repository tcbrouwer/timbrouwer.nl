<template>
  <div id="app">
    <img alt="Stay home chalkboard" src="./assets/sharon-mccutcheon-gxkWSW6K15Y-unsplash_cropped.png">
  <div>Photo by <a href="https://unsplash.com/@sharonmccutcheon?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Sharon McCutcheon</a> on <a href="https://unsplash.com/s/photos/quarantine?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a> (cropped)</div>
  <WelcomeMessage />
  <Categories />
  <Courses />
  <Contact />
  <FAQ />
  </div>
</template>

<script lang="ts">
import Categories from '@/components/Categories.vue'
import Contact from '@/components/Contact.vue'
import Courses from '@/components/Courses.vue'
import FAQ from '@/components/FAQ.vue'
import WelcomeMessage from '@/components/WelcomeMessage.vue'

export default {
  name: 'App',
  components: {
    Categories,
    Contact,
    Courses,
    FAQ,
    WelcomeMessage
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
