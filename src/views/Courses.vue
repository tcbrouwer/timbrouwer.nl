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
// cultuur

// ontspanning
import jongleren from '@/content/ontspanning/jongleren.json'

// tech
import nlp from '@/content/tech/nlp.json'
import queuing from '@/content/tech/queuing.json'


// template
import template from '@/content/template/template.json'

export default {
  name: 'Courses',
  components: {
    CourseCard,
    CourseRequest
  },
  computed: {
    courses() {
      return [
        jongleren, // ontspanning
        nlp, queuing, // tech
        template // template
      ]
    }
  }
}
</script>

<style scoped>
</style>