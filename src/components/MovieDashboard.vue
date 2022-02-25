<template>
  <div class="dashboard">
    <div class="header">
      <div class="menu">
        <ul>
          <li>Homepage</li>
          <li>Series</li>
          <li class="active">Movies</li>
        </ul>
      </div>
      <div class="logo">
        <span>NERDFLIX</span>
      </div>
      <div class="rating_count">
        <span>5</span>
      </div>
    </div>

    <div class="title">
        <h1>Movies</h1>
    </div>

    <div class="filters">
      <div class="search">
        <input name="search" placeholder="Search for a title">
      </div>

      <div class="sort">
        <select v-model="selected_rating">
          <option value="asc" selected>Title (A-Z)</option>
          <option value="desc">Title (Z-A)</option>
        </select>
      </div>
    </div>

    <div class="movies">
      <div v-for="movie in movies" :key="movie.title">
        <MovieCard :movie="movie" />
      </div>
    </div>
  </div>
</template>

<script>
import MovieCard from './MovieCard.vue'

export default {
  name: 'MovieDashboard',
  components: {
    MovieCard
  },
  props: {
    movies: JSON
  },
  data() {
    return {
      selected_rating: 'asc'
    }
  }
}
</script>

<style scoped>
  .header {
    background: #131313;
    height: 75px;
    line-height: 75px;
    display: flex;
    justify-content: space-between;
  }

  .header ul {
    margin: 0;
    padding: 0;
    height: 75px;
  }

  .header li {
    display: inline;
    font-size: 16px;
    margin-left: 50px;
    height: 75px;
  }

  .header .rating_count {
    margin-right: 50px;
  }

  .header .logo {
    color: #E50914;
  }

  .active {
    border-bottom: 4px solid #E50914;
  }

  .title {
    background: #171717;
    height: 122px;
  }

  .title h1 {
    padding-left: 50px;
    font-size: 36px;
    margin: 0px;
    line-height: 122px;
  }

  .movies {
    margin: 80px 50px;
    display: flex;
    flex-wrap: wrap;
  }

  .filters {
    margin: 0 50px;
    display: flex;
    justify-content: space-between;
  }

  input, select {
    color: #FFF;
    background: #131313;
    border: 1px solid #2E2E2E;
    box-sizing: border-box;
    border-radius: 6px;
    padding: 10px;
  }
</style>
