<template>
  <div>
    <h1>Cursus aanbod</h1>
    
    <div>
      <b-card-group class="m-5" deck>
        <CourseCard v-for="course in courses" :key=course.name
          :course = course
        />
      </b-card-group>
    </div>  
  </div>
</template>

<script lang="ts">
import CourseCard from '@/components/CourseCard.vue'

// This is a stub, should load from server
import courses from '@/content/courses.json'
import externals from '@/content/externals.json'

export default {
  name: 'Courses',
  components: {
    CourseCard,
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
      this.courses = courses.concat( externals )
    }
  }
}
</script>

<style scoped>
</style>