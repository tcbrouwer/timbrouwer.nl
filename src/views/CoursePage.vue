<template>
  <div>
    <h1>{{ course.title }}</h1>
    
    <div v-for="step in course.steps" :key="step.title" class="d-flex justify-content-center">
        <StepCard :step = step />
    </div>  
  </div>
</template>

<script lang="ts">
import StepCard from '@/components/StepCard.vue'

// This is a stub, should load from server
import chinees from '@/content/courses/chinees.json'
import defaultCourse from '@/content/courses/default.json'
import jongleren from '@/content/courses/jongleren.json'
import zelf from '@/my_content/stappen.json'


export default {
  name: 'CoursePage',
  props: [ "courseName" ],
  components: {
    StepCard,
  },
  data() {
    return {
      chinees: chinees,
      jongleren: jongleren
    }
  },
  computed: {
    course() {
      // this is a stub, should fetch from server
      if( this.courseName === "chinees" ) {
        return chinees
      } else if( this.courseName === "jongleren") {
        return jongleren
      } else if( this.courseName === "zelf" ) {
        return zelf
      } else {
        return defaultCourse
      }
    }
  }
}
</script>

<style scoped>
</style>