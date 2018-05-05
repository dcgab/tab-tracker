<template>
  <div>
    <h1>Register</h1>

    <input
      type="email"
      name="email"
      v-model.lazy="email"
      placeholder="email">
      <br>
      <input
      type="password"
      name="password"
      v-model="password"
      placeholder="password">
      <br>
      <button v-on:click="register">Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'

export default {
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  methods: {
    async register () {
      let response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<style scoped>

</style>
