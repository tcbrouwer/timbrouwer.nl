<template>
  <div>
    <h1>Cursus aanbod (Concept)</h1>

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
import code4nl from "@/content/code4nl.json";
import courses from "@/content/courses.json";
import zelfdoen from "@/my_content/zelfdoen.json";
import externals from "@/content/externals.json";

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
      this.courses = courses.concat(zelfdoen).concat(externals).concat(code4nl);
    },
  },
};
</script>

<style scoped>
</style>