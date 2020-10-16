<template>
  <div>
    <h1>Cursus Chinees (Concept)</h1>
    
    <div>
      <b-card-group class="m-5" deck>
        <StepCard v-for="step in steps" :key="step.title"
          :step = step
        />
      </b-card-group>
    </div>  
  </div>
</template>

<script lang="ts">
import StepCard from '@/components/StepCard.vue'

// This is a stub, should load from server
import chinees from '@/content/courses/chinees.json'

export default {
  name: 'CoursePageConcept',
  components: {
    StepCard,
  },
  data() {
    return {
      steps: []
    }
  },
  mounted() {
    this.getSteps()
  },
  methods: {
    getSteps() {
      // This should become an API call to server
      // Also this is a concept, and not yet generic
      this.steps = chinees
    }
  }
}
</script>

<style scoped>
</style>