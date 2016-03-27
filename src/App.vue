<template>
  <div id="app">
    <p>{{ message }}</p>
    <input v-model="message">
  </div>
  <comp-a></comp-a>
</template>

<script>
import CompA from './components/A.vue'

export default {
  data() {
    return {
      message: 'Hello Vue.js!'
    }
  },
  components: {
    CompA
  }
}
</script>