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


export default {
  name: 'Categories',
  components: {
    CategoryCard
  },
  data() {
    return {
      categories: [ 
          { name: "Tech" },
          { name: "Cultuur" },
          { name: "Doe het zelf" },
          { name: "Ontspanning" }
      ]
    }
  }
}
</script>

<style scoped>
</style>