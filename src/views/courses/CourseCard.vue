<template>
    <b-card 
        :img-src="picurl" 
        img-alt="vue" 
        img-top
        style="min-width: 20rem; max-width: 25rem"
    >
        <b-card-title>{{course.name}}</b-card-title>
        <b-card-sub-title class="mb-2">Door {{course.door}}</b-card-sub-title>
        <b-card-text>
            {{course.flavortext}}
        </b-card-text>
        <b-list-group flush>
        <b-list-group-item>Doelgroep: {{course.doelgroep}}</b-list-group-item>
        <b-list-group-item>Duur: {{course.duur}}</b-list-group-item>
        <b-list-group-item>Moment: {{course.moment}}</b-list-group-item>
        <b-list-group-item>Kosten: {{course.kosten}}</b-list-group-item>
        </b-list-group>
        <template v-slot:footer>
        <a :href="course.link">Ga naar de cursus/site!</a>
        </template>
    </b-card> 
</template>

<script lang="ts">
export default {
  name: 'CourseCard',
  props: ['course'],
  data() {
      return {
          picurl: "https://picsum.photos/200/200?random=" + Math.random()  
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