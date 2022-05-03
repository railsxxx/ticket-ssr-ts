<template>
  <div class="root">
    <p>Showing {{ filteredTitles.length }} results for "{{ query }}"</p>
    <ul>
      <li v-for="title in filteredTitles" :key="title.id">
        {{ title.Name }}
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { computed } from "vue";
import titles from "./articles.json";

const props = defineProps({
  query: String,
});

const filteredTitles = computed(() => {
  //console.dir(titles[0]);
  return titles.filter((s) => {
    if (props.query) {
      s.Name.toLowerCase().includes(props.query.toLowerCase());
    }
  });
});
</script>
