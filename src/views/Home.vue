<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <h1>Yeet lol</h1>

    <form @submit.prevent= "searchMovies" >
<input type="text" placeholder="search something ya lil shit" v-model="query">
<button class="btn btn-primary btn-sm rounded-pill" @click="searchMovies()">search</button>
    </form>
{{movies}}
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  data() {
    return {
      query: ""
    }
  },
  copmuted: {
    movies() {
      return this.$store.state.results
    }
  },
  methods: {
    searchMovies() {
      this.$store.dispatch('searchApi', this.query)
    }
  },
  components: {}
}
</script>
