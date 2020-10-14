<template>
  <div>
    <h1>Cursus aanbod</h1>
    
    <div>
      <b-card-group class="m-5" deck>
        <CourseCard v-for="course in courses" :key=course.id
          :title = course.title
        />
      </b-card-group>
    </div>  
  </div>
</template>

<script lang="ts">
import CourseCard from './courses/CourseCard.vue'

export default {
  name: 'Courses',
  components: {
    CourseCard
  },
  data() {
    return {
      courses: [
        {
          id: 0,
          title: "Vue from scratch"
        },
        {
          id: 1,
          title: "Word vrienden met je hamster ... online!"
        },
        {
          id: 2,
          title: "Tech or Art. Appreciating(?) artificially generated art"
        },
        {
          id: 3,
          title: "Microbiology 101, what's in a virus?"
        },
        {
          id: 4,
          title: "Zelf brood bakken 1"
        },
        {
          id: 5,
          title: "Zelf brood bakken 2"
        },
        {
          id: 6,
          title: "Zelf brood bakken 3"
        },
        {
          id: 7,
          title: "Zelf brood bakken 4"
        }
      ]
    }
  }
}
</script>

<style scoped>
</style>