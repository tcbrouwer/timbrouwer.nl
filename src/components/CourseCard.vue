<template>
  <b-card
    :img-src="trainer.avatar"
    img-alt="vue"
    img-top
    style="min-width: 15rem; max-width: 25rem"
    class="mb-5"
  >
    <b-card-title>{{ name }}</b-card-title>
    <b-card-sub-title class="mb-2">Trainer: {{ trainer.name }}</b-card-sub-title>
    <b-card-text>
      {{ description }}
    </b-card-text>
    <b-list-group flush>
      <b-list-group-item>Doelgroep: {{ audience }}</b-list-group-item>
      <b-list-group-item>Duur: {{ duration }}</b-list-group-item>
      <b-list-group-item>Moment: {{ start }}</b-list-group-item>
      <b-list-group-item>Kosten: {{ cost }}</b-list-group-item>
    </b-list-group>
    <template v-slot:footer>
      <a :href="link.url">{{ link.text }}</a>
    </template>
  </b-card>
</template>

<script lang="ts">
export default {
  name: "CourseCard",
  props: ["course"],
  computed: {
    audience() {
      return this.course.audience ? this.course.audience : "Iedereen"
    },
    cost() {
      return this.course.cost ? this.course.cost: "Onbekend"
    },
    description() {
      return this.course.description ? this.course.description : "Geen beschrijving beschikbaar"
    },
    duration() {
      return this.course.duration ? this.course.duration : "Onbekend"
    },
    link() {
      if( this.course.link === undefined ) {
        return { url: "", text: "Nog geen link" }
      } else {
        return {
          url: this.course.link.url ? this.course.link.url : "",
          text: this.course.link.text ? this.course.link.text : "Meer informatie"
        }
      }
    },
    name() {
      return this.course.name ? this.course.name : "" // name is used as key, so it should not be missing
    },
    start() {
      return this.course.start ? this.course.start : "Onbekend"
    },
    trainer() {
      if( this.course.trainer === undefined ) {
        return { name: "Onbekend", avatar: this.randomPic() }
      } else {
        return {
          name: this.course.trainer.name ? this.course.trainer.name : "Onbekend",
          avatar: this.course.trainer.avatar ? this.course.trainer.avatar : this.randomPic()
        }
      }
    },      
  },
  methods: {
    randomPic() {
      return "https://picsum.photos/200/200?random=" + Math.random()
    }
  }
};
</script>

<style scoped>
.b-card {
  max-width: 40rem;
  min-width: 40rem;
}
</style>