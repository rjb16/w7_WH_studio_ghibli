<template>
  <div>
    <li v-on:click="handleClick" class="film-list-item">
          {{film.title}}
    </li>

  </div>
</template>

<script>
import { eventBus } from '@/main.js'
export default {
    name: 'film-list-item',
    props: ['film'],
    methods: {
        handleClick() {
            eventBus.$emit('selected-film', this.film)
        },
    }
}
</script>

<style>
</style>