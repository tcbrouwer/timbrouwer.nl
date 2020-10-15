<template>
  <b-card
    :img-src="picurl()"
    img-alt="vue"
    img-top
    style="min-width: 20rem; max-width: 25rem"
  >
    <b-card-title>{{ course.name }}</b-card-title>
    <b-card-sub-title class="mb-2">Trainer: {{ name() }}</b-card-sub-title>
    <b-card-text>
      {{ description() }}
    </b-card-text>
    <b-list-group flush>
      <b-list-group-item>Doelgroep: {{ audience() }}</b-list-group-item>
      <b-list-group-item>Duur: {{ duration() }}</b-list-group-item>
      <b-list-group-item>Moment: {{ start() }}</b-list-group-item>
      <b-list-group-item>Kosten: {{ costs() }}</b-list-group-item>
    </b-list-group>
    <template v-slot:footer>
      <a :href="course.link">Ga naar de cursus/site!</a>
    </template>
  </b-card>
</template>

<script lang="ts">
export default {
  name: "CourseCard",
  props: ["course"],
  data() {
    return {
      picurl: () => {
        if (this.course.trainer && this.course.trainer.avatar) {
          return this.course.trainer.avatar;
        }
        return "https://picsum.photos/200/200?random=" + Math.random();
      },
      name: () => {
        return this.course.door ? this.course.door : this.course.trainer.name;
      },
      description: () => {
        return this.course.flavortext
          ? this.course.flavortext
          : this.course.description;
      },
      duration: () => {
        return this.course.duur ? this.course.duur : this.course.duration;
      },
      start: () => {
        return this.course.moment || this.course.start;
      },
      costs: () => {
        return this.course.kosten || this.course.cost;
      },
      audience: () => {
        return this.course.doelgroep || this.course.audience;
      },
    };
  },
};
</script>

<style scoped>
.b-card {
  max-width: 40rem;
  min-width: 40rem;
}
</style>