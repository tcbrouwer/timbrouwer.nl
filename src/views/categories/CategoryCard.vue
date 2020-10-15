<template>
    <b-card 
        :img-src="url" 
        img-alt="vue" 
        img-top
        style="min-width: 25rem; max-width: 30rem"
    >
        <b-card-title>{{name}}</b-card-title>
        
    </b-card>

</template>

<script lang="ts">
export default {
  name: 'CategoryCard',
  props: ['name'],
  data() {
      return {
          url: "https://picsum.photos/200/200?random=" + Math.random()  
      }
  }
}
</script>

<style scoped>
.b-card {
    max-width: 40rem;
    min-width: 40rem;
}
</style>