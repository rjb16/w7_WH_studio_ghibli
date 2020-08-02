<template>
  <div>
    <h1>Studio Ghibli Films</h1>
    <div class="main-container">
      <film-list :films='films'></film-list>
      <film-detail :film="selectedFilm"></film-detail>
    </div>
  </div>
</template>

<script>
import { eventBus } from "@/main.js"
import FilmList from "./components/FilmList.vue"
import FilmDetail from "./components/FilmDetail.vue"

export default {
  name: 'app',
  data() {
    return {
      films: [],
      selectedFilm: null
    };
  },
  mounted() {
    fetch('https://ghibliapi.herokuapp.com/films')
    .then(response => response.json())
    .then(films => this.films = films)
    
    eventBus.$on('selected-film', (film) => {this.selectedFilm = film})
  },
  components: {
    "film-list": FilmList,
    "film-detail": FilmDetail
  }
}
</script>

<style>
</style>