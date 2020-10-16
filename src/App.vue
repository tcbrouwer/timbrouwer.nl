<template>
  <div id="app">
    <Welcome />
    <router-view />
  </div>
</template>

<script lang="ts">
import Welcome from "@/views/Welcome.vue"

export default {
  name: 'App',
  components: {
    Welcome
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif; */
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>