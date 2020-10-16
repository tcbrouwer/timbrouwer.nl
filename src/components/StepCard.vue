<template>
  <b-card
    style="min-width: 15rem; max-width: 25rem;"
    class="m-3"
  >
    <b-card-title>            
        <span v-html="title" />
    </b-card-title>
    <b-list-group flush>
        <b-list-group-item v-for="text in texts" :key="text">
            <span v-html="text" />
        </b-list-group-item>
    </b-list-group>
    <template v-slot:footer>
      <a :href="link.url">{{ link.text }}</a>
    </template>
  </b-card>
</template>

<script lang="ts">
export default {
  name: "StepCard",
  props: ["step"],
  computed: {
    title() {
      return this.step.title ? this.step.title : "Volgende stap"
    },
    texts() {
      return this.step.text ? this.step.text : [ "Instructies volgen nog" ]
    },
    link() {
      if( this.step.link === undefined ) {
        return { url: "", text: "Nog geen link" }
      } else {
        return {
          url: this.step.link.url ? this.step.link.url : "",
          text: this.step.link.text ? this.step.link.text : "Meer informatie"
        }
      }
    }     
  },
};
</script>

<style scoped>
</style>