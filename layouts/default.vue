<template>
  <div>
    <div v-if="$auth.loggedIn">
      {{ $auth.user.email }}
      <b-button variant="danger">logout</b-button>
    </div>
    <div v-else>
      not logged in
      <b-button variant="primary">login</b-button>
      <b-button variant="outline-primary">register</b-button>
    </div>
    <Nuxt />
  </div>
</template>

<style>
</style>
