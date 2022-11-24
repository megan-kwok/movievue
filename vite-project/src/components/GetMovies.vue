<script setup>
import { ref } from "vue"
import axios from "axios"
 
const movies = ref("");
const response = ref(null);
 
const getMovies = async () => {
   response.value = (
  await axios.get(`https://api.themoviedb.org/3/movie/${id}`, {
    params: {
      api_key: "26ca7d300d9e397095fa7e1435f5eb3d",
    },
  })
).data;
}
axios(getMovies)
  .then(data => console.log(data))
  .catch(error => console.log(error))
</script>
 
<template>
      <select v-model="movies" id="movies">
            <option value="483455">Dead Apple</option>
            <option value="198663">The Maze Runner</option>
            <option value="575813">Better days</option>
            <option value="76826">Grave of the Fireflies</option>
            <option value="851644">20th Century Girl</option>
            <option value="88751">Journey to the Center of the Earth</option>
            <option value="730154">Your Eyes Tell</option>
            <option value="433422">Fairy Tail: Dragon Cry</option>
            <option value="329">Jurassic Park I</option>
            <option value="497582">Enola Holmes II</option>
        </select>
        <button @click="getMovies">Get</button>
        <div v-if="response" class="movies-container">
        <h1>{{ response.movies.title }}</h1>
        <p>{{ response.overview }}</p>
        <p>{{ response.runtime }}</p>
        <p>{{ response.release_date }}</p>
        <p>{{ response.popularity }}</p>
        <p>{{ response.budget }}</p>
        <p>{{ response.vote_average }}</p>
        <p>{{ response.original_language }}</p>
        <img v-bind:src="'http://image.tmdb.org/t/p/w500/' +     response.poster_path" width='100px'>
        <img v-bind:src="'http://image.tmdb.org/t/p/w500/' +     response.backdrop_path" width='100px'> -->
    </div>
</template>
 
<style scoped>
div p {
  text-align: center;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
</style>