<template>
  <List
    @on-item-selected="onMovieSelected"
    :dataList="movieList"
    :selectedId="selectedId"
  />
</template>

<script setup>
import { defineProps, defineEmits, inject } from "vue";
import List from "./List.vue";

const props = defineProps({
  movieList: Array,
  selectedId: String,
});

const emit = defineEmits(["on-movie-selected"]);

const setPageTitle = inject("setPageTitle");

function onMovieSelected(movieData) {
  emit("on-movie-selected", movieData);
  setPageTitle(movieData.title);
}
</script>


