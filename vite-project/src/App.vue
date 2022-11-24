<script setup>
import GetMovies from "./components/GetMovies.vue";

</script>

<template>
  <div class="app-container">
    <Suspense>
      <GetMovies />
    </Suspense>
    </div>
</template>

<style scoped>
* {
  margin: 0px;
  padding: 0px;
}

.app-container {
  display: grid;
  grid-template-columns: repeat (10 , 1fr);
  grid-template-rows: repeat (10 , 1fr)
}
</style>
