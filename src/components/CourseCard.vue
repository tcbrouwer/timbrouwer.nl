<template>
    <b-card 
        img-src="favicon.ico" 
        img-alt="vue" 
        img-top
        style="min-width: 20rem; max-width: 30rem"
    >
        <b-card-title>{{title}}</b-card-title>
        <b-card-sub-title class="mb-2">Door Bim Trouwer</b-card-sub-title>
        <b-card-text>
        Dit is een filler-course als voorbeeld.
        Gegeven
        </b-card-text>
        <b-list-group flush>
        <b-list-group-item>Doelgroep: alle geïntresseerden met enige Front-end ervaring</b-list-group-item>
        <b-list-group-item>Duur en vorm: Zoom-sessie van 2 uur</b-list-group-item>
        <b-list-group-item>Datum: elke dinsdag om 14:00</b-list-group-item>
        <b-list-group-item>Kosten: Gratis! (bijdrage wordt gewaardeerd)</b-list-group-item>
        </b-list-group>
        <template v-slot:footer>
        <a href="#">Ga naar de site!</a>
        </template>
    </b-card> 
</template>

<script>
export default {
  name: 'CourseCard',
  props: ['title']
}
</script>

<style scoped>
.b-card {
    max-width: 40rem;
    min-width: 40rem;
}
</style>