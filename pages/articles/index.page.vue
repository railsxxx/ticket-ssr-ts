<template>
  <div>
    <h2>Filter Articles</h2>
    <input type="text" placeholder="Filter Search" v-model="query" />
    <button @click="reset">Reset</button>
    {{ query }}
    <SearchResults :query="query" />
  </div>
</template>

<style>
h1,
h2,
p {
  color: red;
}
</style>

<script setup lang=ts>
import SearchResults from "./SearchResults.vue";
import { ref } from "vue";
const query = ref("");

const reset = (evt) => {
  query.value = ""; // clears the query
};
</script>
