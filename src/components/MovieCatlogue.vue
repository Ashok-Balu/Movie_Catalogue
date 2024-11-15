<template>
  <div class="movieWrapper">
    <div class="moviePreview">
      <MoviePreview
        :movieTitle="dataPreview.title"
        :posterUrl="dataPreview.poster"
        :releaseYear="dataPreview.year"
        :director="dataPreview.director"
        :casts="dataPreview.casts"
        :genre="dataPreview.genre"
      />
    </div>
    <div class="movieList">
      <MovieList
        @on-movie-selected="onMovieSelected"
        :movieList="movieList"
        :selectedId="selectedItemId"
      />
    </div>
  </div>
</template>

<script setup>
import { ref, watch } from 'vue';
import MovieList from './MovieList.vue';
import MoviePreview from './MoviePreview.vue';

const props = defineProps({
  movieList: {
    type: Array,
    required: true
  }
});

const selectedItemId = ref(props.movieList[0].id);
const dataPreview = ref(props.movieList[0]);

const emit = defineEmits();

const onMovieSelected = (movieData) => {
  selectedItemId.value = movieData.id;
  dataPreview.value = movieData;
};
</script>

<style scoped>
.movieWrapper {
  height: 100%;
  overflow: hidden;
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  width: 100%;
}

.moviePreview,
.movieList {
  flex: 1 1 50%;
  height: calc(100vh - 60px);
  display: flex;
  flex-direction: column;
  align-items: center;
}

.moviePreview {
  text-align: center;
  margin-right: 1em;
  align-self: flex-start;
}

.movieList {
  text-align: left;
  align-self: flex-end;
}
</style>