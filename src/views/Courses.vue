<template>
  <div>
    <h1>timbrouwer.nl</h1>

    <div>
      <b-card-group class="m-3" deck>
        <CourseCard
          v-for="course in courses"
          :key="courseKey( course )"
          :course="course"
        />
      </b-card-group>
    </div>
  </div>
</template>

<script lang="ts">
import CourseCard from "@/components/CourseCard.vue";

// This is a stub, should load from server
import upstream from "@/news/upstream.json"
import profile from "@/timbrouwer.nl/profile.json"


export default {
  name: "Courses",
  components: {
    CourseCard,
  },
  data() {
    return {
      courses: [],
    };
  },
  mounted() {
    this.getCourses();
  },
  methods: {
    courseKey( course ) {
       return course.name.short ? course.name.short : course.name 
    },
    getCourses() {
      // This should become an API call to server
      this.courses = [].concat( profile ).concat( upstream )
    },
  },
};
</script>

<style scoped>
</style>