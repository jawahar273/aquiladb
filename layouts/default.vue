<template>
  <div>
    <!-- AquilaDB -->
    <b-navbar class="has-shadow">
      <template slot="brand">
        <b-navbar-item href="/">
          <img
            src="https://avatars1.githubusercontent.com/u/37766717?v=4"
          >
        </b-navbar-item>
      </template>
      <template slot="end">
        <b-navbar-item href="#">
          Home
        </b-navbar-item>
        <b-navbar-item href="#">
          Documentation
        </b-navbar-item>
        <b-navbar-item href="#">
          Tutorial
        </b-navbar-item>
        <b-navbar-item href="#">
          Blog
        </b-navbar-item>
        <b-navbar-item href="#">
          Github
        </b-navbar-item>
      </template>
    </b-navbar>

    <section class="main-content columns">
      <div class="container column is-10">
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data () {
    return {
      items: [
        {
          title: 'Home',
          icon: 'home',
          to: { name: 'index' }
        },
        {
          title: 'Inspire',
          icon: 'lightbulb',
          to: { name: 'inspire' }
        }
      ]
    }
  }
}
</script>
