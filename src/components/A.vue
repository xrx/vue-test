<template>
  <div class="container">
    <h2 class="red">{{msg}}</h2>
    <p v-for="item in someData">{{item | json }}</p>
  </div>
</template>

<script>

import { getMessage } from '../services/movies'
export default {
  data () {
    return {
      msg: "Movies",
      someData: this.someData
    }
  },
  activate(done) {
    var self = this
    var msg = this.$http({url: 'http://localhost:8090/api/movies', method: 'GET'})
    msg.then(function (response) {
      self.someData = response.data
      done()
    }).catch(function (response) {
      alert("aaaah!");
    });
  }
}
</script>