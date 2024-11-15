<template>
  <div>
    <p v-if="!isDataLoaded">Loading movies...</p>
    <MovieCatalogue v-else :movieList="movieData" />
  </div>
</template>

<script setup>
import { ref, onMounted } from "vue";
import MovieCatalogue from "../components/MovieCatlogue.vue";
import dataJson from "../static/movie-data.json";

const movieData = ref([]);
const isDataLoaded = ref(false);

onMounted(() => {
  setTimeout(() => {
    movieData.value = dataJson;
    isDataLoaded.value = true;
  }, 500); 
});
</script>

