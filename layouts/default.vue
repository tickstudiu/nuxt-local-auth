<template>
  <div>
    <div v-if="$auth.loggedIn">
      <small>{{ $auth.user.email }}</small>
      <b-button variant="danger">logout</b-button>
    </div>
    <div v-else>
      <small>not logged in</small>
      <nuxt-link to="/login">login</nuxt-link>
      <nuxt-link to="/register">register</nuxt-link>
    </div>
    <b-container>
      <Nuxt />
    </b-container>
  </div>
</template>

<style>
</style>
