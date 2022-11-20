<script setup>
import axios from 'axios'
const props = defineProps(["api_key", "id"]);
const response = (
  await axios.get(`https://api.themoviedb.org/3/movie/${id}`, {
    params: {
      id: props.id,
      api_key: "26ca7d300d9e397095fa7e1435f5eb3d",
    },
  })
).data;
</script>

<template>
    <div class="movies">
        <div v-for='result in results' :key='result.id'>
        <h1>{{result.title}}</h1>
        <p>{{result.overview}}</p>
        <p>{{result.runtime}}</p>
        <p>{{result.release_date}}</p>
        <p>{{result.popularity}}</p>
        <p>{{result.budget}}</p>
        <p>{{result.vote_average}}</p>
        <p>{{result.original_language}}</p>
        <img v-bind:src="'http://image.tmdb.org/t/p/w500/' +    result.poster_path" width='100px'>
        <img v-bind:src="'http://image.tmdb.org/t/p/w500/' +    result.backdrop_path" width='100px'>
    </div>
    </div>
</template>

<style scoped>

</style>