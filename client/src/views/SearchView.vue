<script setup lang="ts">
import ResultCard from "@/components/search/ResultCard.vue";

const results = [
  {
    id: "fuckids",
    title: "How to shoot yourself in a foot with C++20",
    date: "September 2021", // TODO: Replace String with proper type for dates (luxon!)
    thumbnailUrl: "/sutter.jpg",
    author: "Herb Sutter",
    description:
      "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.",
  },
  {
    id: "something",
    title: "Something else",
    date: "September 2021", // TODO: Replace String with proper type for dates (luxon!)
    thumbnailUrl: "/sutter.jpg",
    author: "Herb Sutter",
    description: "",
  },
];
</script>

<template>
  <div class="search">
    <div class="filters">filter</div>
    <div class="results">
      <ResultCard v-for="result in results" v-bind="result" :key="result.id" />
    </div>
  </div>
</template>

<style scoped>
.search {
  padding-inline: 3rem;
  display: grid;
  grid-template-columns: minmax(0, auto) 2fr;
  column-gap: 3em;
}
.results {
  display: grid;
}
</style>
