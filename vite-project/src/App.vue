<script setup>
import MovieSelect from "./components/GetMovies.vue";
</script>

<template>
    <div id="MovieSelect">
        <select v-model="Movies" id="Movies">
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
        <button v-on:click="getMovies">Get</button>
    </div>
</template>

<style scoped>

</style>
