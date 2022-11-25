<script setup>
import { ref } from 'vue'
import axios from 'axios'
 
const movies = ref("");
const response = ref(null);
 
const getMovies = async () => {
  response.value = (
    await axios.get(`https://api.themoviedb.org/3/movie/${movies.value}`, {
      params: {
        api_key: "26ca7d300d9e397095fa7e1435f5eb3d",
      },
    })
  ).data;
  console.log(response.value);
}
</script>
 
<template>
    <link href="https://fonts.googleapis.com/css2?family=Rubik+Bubbles&display=swap" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Titan+One&display=swap" rel="stylesheet">
  <div class="select-container">
    <h1 class="header">My Favourite Movies!</h1>
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
  <button @click="getMovies" id="get">Get</button>
  <div v-if="response" class="movies-container">
    <h1>{{ response.title }}</h1>
    <p>{{ response.overview }}</p>
    <p>Runtime: {{ response.runtime }}</p>
    <p>Release Date: {{ response.release_date }}</p>
    <p>Popularity: {{ response.popularity }}</p>
    <p>Budget: {{ response.budget }}</p>
    <p>Vote Average: {{ response.vote_average }}</p>
    <p>Original Language: {{ response.original_language }}</p>
    <img :src="`http://image.tmdb.org/t/p/w500/${response.poster_path}`" id="poster">
    <img :src="`http://image.tmdb.org/t/p/w500/${response.backdrop_path}`" id="backdrop">
  </div>
</div>
</template>
 
<style scoped>
body {
  background-color: rgb(143, 72, 139);
}
.select-container {
  display: grid;
  grid-template-columns: repeat (10 , 1fr);
  grid-template-rows: repeat (10 , 1fr);
  background-color: rgb(143, 72, 139);
}
.select-container > .header {
  border-color: black;
  border: 5px;
  text-align: center;
  padding: 2%;
  font-family: 'rubik bubbles' , serif;
  font-size: 3rem;
  color: white;
}
.select-container > #movies {
  margin: 0% 35% 0% 35%;
}
.select-container > #get {
  margin: 0% 35% 0% 35%;
  color: blueviolet;
}
 
/* styling for response elements */
 
.movies-container > h1 {
  padding: 2%;
  font-family: 'titan one' , serif;
  color:  rgb(88, 44, 86);
  font-size: 35px;
  text-align: center;
}
 
.movies-container > p {
  margin: 0% 20% 0% 20%;
  background-color: rgb(221, 169, 231);
  text-align: center;
}
 
.movies-container > img {
  padding: 5px;
  border: 5px;
  background-color: rgb(237, 195, 250);
  border-radius: 2%;
}
 
.movies-container > #poster {
  margin: 1% 0% 0% 10%;
}
 
.movies-container > #backdrop {
  margin: 0% 0% 20% 1%;
}
</style>
