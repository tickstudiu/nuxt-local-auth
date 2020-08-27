<template>
  <div>
    <b-form @submit="onSubmit">
      <b-form-group label="Email:">
        <b-form-input v-model="login.username" type="text" required placeholder="Enter username"></b-form-input>
      </b-form-group>

      <b-form-group label="Password:">
        <b-form-input v-model="login.password" type="password" required placeholder="Enter password"></b-form-input>
      </b-form-group>

      <b-button type="submit" variant="primary">Submit</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ login }}</pre>
    </b-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      login: {
        username: '',
        password: '',
      },
    }
  },
  methods: {
    async onSubmit(evt) {
      evt.preventDefault()

      try {
        let response = await this.$auth.loginWith('local', { username: this.login.username, password: this.login.password})
        console.log(response)
      } catch (err) {
        console.log(err)
      }
    },
  },
}
</script>