<template>
  <div>
    <MovieDashboard :movies="json_data.data.movies"/>
  </div>
</template>

<script>
import MovieDashboard from './components/MovieDashboard.vue'
import filmData from './assets/imdb-top-50.json'

export default {
  name: 'App',
  components: {
    MovieDashboard
  },
  data() {
    return {
      json_data: filmData
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro&display=swap');

body {
  margin: 0;
  padding: 0;
  background: #1D1D1D;
}

#app {
  font-family: "Source San Pro", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #FFF;
}
</style>