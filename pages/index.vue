<template>
  <section class="container">
    <div>
      <app-logo/>
      <h1 class="title">
        {{title}}
      </h1>
      <h2 class="subtitle">
        This project name is {{title}}
      </h2>
      <div class="counter">
      <ul>
          <li>
              Counter info: {{$store.state.counter}}
          </li>
          <li>
            <button @click="increment">
              Increment
            </button>
          </li>
          <li>
            <button @click="decrement">
              Decrement
            </button>
          </li>
          <li>
              <nuxt-link to="/count">Go Counter only page.</nuxt-link>
          </li>
      </ul>
      </div>
      <div class="links">
        <a
          href="https://nuxtjs.org/"
          target="_blank"
          class="button--green">Documentation</a>
        <a
          href="https://github.com/nuxt/nuxt.js"
          target="_blank"
          class="button--grey">GitHub</a>
      </div>
    </div>
  </section>
</template>

<script>
import AppLogo from '~/components/AppLogo.vue'
import { mapState } from 'vuex'

export default {
  fetch({ store }) {
    console.log('called fatch');
    console.log(`fetch: ${store.state.counter}`)
  },
  computed: mapState([
    'counter'
  ]),
  methods: {
    increment() {
      this.$store.commit('increment')
    },
    decrement() {
      this.$store.commit('decrement')
    }
  },
  data () {
    console.log('called data')
    return { title: 'default title' }
  },
  asyncData ({ store }) {
    console.log('called asyncData')
    console.log(`asyncData: ${store.state.counter}`)
    return { title: 'Hello nuxt.js' }
  },
  components: {
    AppLogo
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
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif; /* 1 */
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
