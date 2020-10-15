<template>
  <div>
    <h1>Cursus aanbod</h1>
    
    <div>
      <b-card-group class="m-5" deck>
        <CourseCard v-for="course in courses" :key=course.name
          :course = course
        />
        <CourseRequest />
      </b-card-group>
    </div>  
  </div>
</template>

<script lang="ts">
import CourseCard from './courses/CourseCard.vue'
import CourseRequest from './courses/CourseRequest.vue'

// This is a stub, should load from server
import courses from '@/content/courses.json'

export default {
  name: 'Courses',
  components: {
    CourseCard,
    CourseRequest
  },
  data() {
    return {
      courses: []
    }
  },
  mounted() {
    this.getCourses()
  },
  methods: {
    getCourses() {
      // This should become an API call to server
      this.courses = courses
    }
  }
}
</script>

<style scoped>
</style>