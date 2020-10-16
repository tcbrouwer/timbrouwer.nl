<template>
  <div>
    <h1>{{ title }}</h1>
    
    <div v-for="step in steps" :key="step.title" class="d-flex justify-content-center">
        <StepCard :step = step />
    </div>  
  </div>
</template>

<script lang="ts">
import StepCard from '@/components/StepCard.vue'



export default {
  name: 'CoursePageConcept',
  props: [ "steps", "title" ],
  components: {
    StepCard,
  },
}
</script>

<style scoped>
</style>