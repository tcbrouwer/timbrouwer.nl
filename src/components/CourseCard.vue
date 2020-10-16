<template>
  <b-card
    :img-src="mentor.avatar"
    img-alt="avatar"
    img-top
    style="min-width: 15rem; max-width: 25rem"
    class="m-3"
  >
    <b-card-title>{{ name }}</b-card-title>
    <b-card-sub-title class="m-2"
      >{{ mentor.role }}: {{ mentor.name }}</b-card-sub-title
    >
    {{course.name.short}}
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
      <router-link v-if="isInternal" :to="link.url">
        {{ link.text }}
      </router-link>
      <a v-else :href="link.url">{{ link.text }}</a>
    </template>
  </b-card>
</template>

<script lang="ts">
export default {
  name: "CourseCard",
  props: ["course"],
  computed: {
    audience() {
      return this.course.audience ? this.course.audience : "Iedereen";
    },
    cost() {
      return this.course.cost ? this.course.cost : "Onbekend";
    },
    description() {
      return this.course.description
        ? this.course.description
        : "Geen beschrijving beschikbaar";
    },
    duration() {
      return this.course.duration ? this.course.duration : "Onbekend";
    },
    isInternal() {
      return this.link.url === undefined
    },
    link() {
      const defaultURL = "/courses/" + this.course.name.short
      const defaultText = "Lees verder!"
      if (this.course.link === undefined) {
        return { url: defaultURL, text: defaultText };
      } else {
        return {
          url: this.course.link.url ? this.course.link.url : defaultURL,
          text: this.course.link.text
            ? this.course.link.text
            : defaultText,
        };
      }
    },
    name() {
      // name is used as key, so it should not be missing
      if( this.course.name === undefined ) {
        return ""
      } else if( this.course.name.full ) {
        return this.course.name.full   
      } else {
        return this.course.name
      }
    },
    start() {
      return this.course.start ? this.course.start : "Onbekend";
    },
    mentor() {
      if (this.course.mentor === undefined) {
        return { name: "Onbekend", role: "Mentor", avatar: this.randomPic() };
      } else {
        return {
          name: this.course.mentor.name ? this.course.mentor.name : "Onbekend",
          role: this.course.mentor.role ? this.course.mentor.role : "Mentor",
          avatar: this.course.mentor.avatar
            ? this.course.mentor.avatar
            : this.randomPic(),
        };
      }
    },
  },
  methods: {
    randomPic() {
      return "https://picsum.photos/200/200?random=" + Math.random();
    },
  },
};
</script>

<style scoped>
</style>