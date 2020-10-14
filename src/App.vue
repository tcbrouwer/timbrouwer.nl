<template>
  <div id="app">
    <img alt="Stay home chalkboard" src="./assets/sharon-mccutcheon-gxkWSW6K15Y-unsplash_cropped.png">
  <div>Photo by <a href="https://unsplash.com/@sharonmccutcheon?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Sharon McCutcheon</a> on <a href="https://unsplash.com/s/photos/quarantine?utm_source=unsplash&amp;utm_medium=referral&amp;utm_content=creditCopyText">Unsplash</a> (cropped)</div>
  <WelcomeMessage />
  <Categories />
  <Courses />
  <TipList />
  <Contact />
  <FAQ />
  </div>
</template>

<script lang="ts">
import Categories from '@/views/Categories.vue'
import Contact from '@/views/Contact.vue'
import Courses from '@/views/Courses.vue'
import FAQ from '@/views/FAQ.vue'
import TipList from '@/views/TipList.vue'
import WelcomeMessage from '@/views/WelcomeMessage.vue'

export default {
  name: 'App',
  components: {
    Categories,
    Contact,
    Courses,
    FAQ,
    TipList,
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
