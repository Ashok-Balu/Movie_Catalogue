<template>
  <div class="movie-preview-container">
    <img class="image" :src="posterUrl" :alt="movieTitle" />
    <div class="movie-content-container">
      <h3>{{ movieTitle }} ({{ releaseYear }})</h3>
      <div>
        <span>
          <strong>Director: </strong>
        </span>
        <span>{{ director }}</span>
      </div>
      <div>
        <span>
          <strong>Cast: </strong>
        </span>
        <span>{{ casts }}</span>
      </div>
      <div>
        <span>
          <strong>Genre: </strong>
        </span>
        <span>{{ genre }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  movieTitle: String,
  posterUrl: String,
  releaseYear: String,
  director: String,
  casts: String,
  genre: String,
});
</script>

<style scoped>
.movie-previe-container {
  padding-top: 10px;
  padding-left: 15em;
}

.movie-content-container{
  padding-right: 15em;
}

.image {
  border-radius: 5%;
  padding-right: 15em;
  max-width: 48vh;
  max-height: 60vh;
  width: auto;
  height: auto;
}
</style>
