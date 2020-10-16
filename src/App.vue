<template>
  <div id="app">
    <img src="@/assets/logo.png" />
    <WelcomeMessage />
    <Courses />
    <hr>
    <FAQ />
    <CoursePageConcept :steps="chinees" title="Cursus Chinees" />
    <hr>
    <CoursePageConcept :steps="jongleren" title="Leer jongleren in 2 weken" />
    <hr>
  </div>
</template>

<script lang="ts">
import Courses from '@/views/Courses.vue'
import CoursePageConcept from '@/views/CoursePageConcept.vue'
import FAQ from '@/views/FAQ.vue'
import WelcomeMessage from '@/views/WelcomeMessage.vue'

// This is a stub, should load from server
import chinees from '@/content/courses/chinees.json'
import jongleren from '@/content/courses/jongleren.json'

export default {
  name: 'App',
  components: {
    Courses,
    CoursePageConcept,
    FAQ,
    WelcomeMessage
  },
  data() {
    return {
      chinees: chinees,
      jongleren: jongleren
    }
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
