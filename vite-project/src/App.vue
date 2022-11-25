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
.app-container {
  background-color: rgb(143, 72, 139);
}
</style>

