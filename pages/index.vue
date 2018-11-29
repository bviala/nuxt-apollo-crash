<template>
  <section class="container">
    <div>
      <logo/>
      <h1 class="title">
        nuxt-apollo-crash
      </h1>
    </div>
    <br>
    <div
      v-for="(continent, index) in continents"
      :key="index">
      {{ continent.code }} <br>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import gql from "graphql-tag"

const continentsQuery = gql`query{continents{code}}`

export default {
  components: {
    Logo
  },
  apollo: {
    continents: {
      query: continentsQuery,
      // update: data => data.continents // correct line, works fine
      // update: data => data.foo // incorrect key, nothing happens
      update: data => data.foo.bar // incorrect key, throw a TypeError that makes the server crash
    }
  }
}
</script>

<style>

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
