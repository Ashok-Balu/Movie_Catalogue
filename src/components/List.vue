<template>
  <div class="movie-list">
    <div
      class="movie-litem"
      v-for="(item, index) in dataList"
      :key="index"
      v-on:click="onItemSelected(item)"
    >
      <a href="#" :class="{ active: item.id === selectedId }">
        {{ item.title }}
      </a>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

const props = defineProps({
  dataList: {
    type: Array,
    required: true
  },
  selectedId: {
    type: String,
    required: true
  }
});

const emit = defineEmits();

const onItemSelected = (itemData) => {
  emit("on-item-selected", itemData);
};
</script>

<style scoped>
.movie-litem {
  height: 30px;
}
.movie-list {
  background-color: #ececec;
  height: 100%;
  padding-left: 2em;
  padding-right: 15em;
  padding-top: 1em;
  width: 100%;
  display: flex;
  flex-direction: column;
}

a {
  background-color: #ececec;
  font-weight: normal;
  cursor: pointer;
  padding-left: 0.75em;
  padding-right: 0.75em;
  padding-top: 0.2em;
  padding-bottom: 0.2em;
  color: #1a1a1a;
  text-decoration: none;
  width: 100%;
  display: block;
}
a.active {
  background-color: #a9b3c4;
  font-weight: bold;
}
</style>
