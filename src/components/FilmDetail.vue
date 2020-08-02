<template>
  <div v-if="film">
      <h2>{{film.title}}</h2>
      <ul>
          <li>Title: {{film.title}}</li>
          <li>Director: {{film.director}}</li>
          <li>Release Date: {{film.release_date}}</li>
          <li>RottenTomato Score: {{film.rt_score}}</li>
          <li>Description: {{film.description}}</li>
      </ul>

  </div>
</template>

<script>
export default {
    name: 'film-detail',
    props: ['film']
}
</script>

<style>
</style>