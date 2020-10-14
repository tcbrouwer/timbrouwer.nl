<template>
    <b-card 
        :img-src="picurl" 
        img-alt="vue" 
        img-top
        style="min-width: 20rem; max-width: 30rem"
    >
        <b-card-title>Request a course</b-card-title>
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
            <b-form-group
                id="input-group-1"
                label="Email address:"
                label-for="input-1"
                description="We'll never share your email with anyone else."
            >
                <b-form-input
                id="input-1"
                v-model="form.email"
                type="email"
                required
                placeholder="Enter email"
                ></b-form-input>
            </b-form-group>

            <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
                <b-form-input
                id="input-2"
                v-model="form.name"
                required
                placeholder="Enter name"
                ></b-form-input>
            </b-form-group>

            <b-form-group id="input-group-3" label="Je verzoek:" label-for="input-3">
                <b-form-input
                id="input-3"
                v-model="form.request"
                required
                placeholder="Enter request"
                ></b-form-input>
            </b-form-group>

            <b-button type="submit" variant="primary">Submit</b-button>
            <b-button type="reset" variant="danger">Reset</b-button>
        </b-form>
    </b-card> 
</template>

<script lang="ts">
export default {
  name: 'CourseRequest',
  data() {
      return {
        picurl: "https://picsum.photos/200/200?random=" + Math.random(),
        form: {
          email: '',
          name: '',
          request: '',
        },
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert("This is a mock implementation, your data is: " + JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.request = ''
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
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