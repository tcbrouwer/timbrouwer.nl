<template>
  <div>
   
    <div>
      <b-card-group class="m-5" deck>
        <CategoryCard v-for="category in categories" :key=category.name
          :name = category.name
        />
      </b-card-group>
    </div>  
  </div>
</template>

<script lang="ts">
import CategoryCard from './categories/CategoryCard.vue'

// This is a stub, should load from server
import cultuur from '@/content/cultuur.json'
import ontspanning from '@/content/ontspanning.json'
import tech from '@/content/tech.json'
// import template from '@/content/template.json'


export default {
  name: 'Categories',
  components: {
    CategoryCard
  },
  computed: {
    categories() {
      return [
        cultuur, ontspanning, tech, // template
      ]
    }
  }
}
</script>

<style scoped>
</style>