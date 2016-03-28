<template>
  <div class="container">
    <movie v-for="movie in movies"
           :movie="movie">
  </div>
</template>

<script>

import { getMessage } from '../services/movies'
import Movie from './Movie.vue'

export default {
  components: {
    Movie
  },
  data () {
    return {
      movies: this.movies
    }
  },
  activate(done) {
    var self = this
    var msg = this.$http({url: 'http://localhost:8090/api/movies', method: 'GET'})
    msg.then(function (response) {
      self.movies = response.data
      done()
    }).catch(function (response) {
      alert("aaaah!");
    });
  }
}
</script>
