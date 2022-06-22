<script setup lang="ts">
import Button from "@/components/Button.vue";
import AuthorSpot from "@/components/AuthorSpot.vue"
import router from "@/router"

var categories = [
  { icon: "bi-braces", id: "core", name: "Core Language", size: 0},
  { icon: "bi-diagram-3", id: "design", name: "Software Design", size: 0},
  { icon: "bi-bar-chart", id: "structures", name: "Data Structures", size: 3},
  { icon: "bi-shuffle", id: "multithreading", name: "Multithreading", size: 0},
  { icon: "bi-memory", id: "memory", name: "Memory management", size: 10},
  { icon: "bi-speedometer2", id: "optimization", name: "Optimizations", size: 0},
  { icon: "bi-hdd-network", id: "networking", name: "Networking", size: 0},
  { icon: "bi-list-columns", id: "compilers", name: "Compilers", size: 0},
  { icon: "bi-gpu-card", id: "gpgpu", name: "GPGPU", size: 0},
  { icon: "bi-boxes", id: "embedded", name: "Embedded Systems", size: 50},
  { icon: "bi-gear", id: "tools", name: "Tools", size: 0},
  { icon: "bi-journal-bookmark", id: "education", name: "Education", size: 0},
]

var authors = [
  { icon: "/aa.jpg", name: "Alexandrescu" },
  { icon: "/bs.jpg", name: "Stroustrup" },
  { icon: "/meyers.jpg", name: "Meyers" },
  { icon: "/sutter.jpg", name: "Sutter" },
  { icon: "/j.jpg", name: "Josuttis" },
  { icon: "/l.png", name: "Lavavej" },
  { icon: "/car.jpg", name: "Carruth" },
]

function openCategory(category: any, e: any) {
  router.push({ path: "/search", query: { category: category.id } });
}

function openAuthor(author: any, e: any) {
  router.push({ path: "/search", query: { author: author.name } });
}
</script>

<template>
  <div class="mx-5 mb-5 d-flex flex-row authors">
    <AuthorSpot v-for="author in authors" 
      :picture="author.icon"
      @click="(e) => openAuthor(author, e)">{{ author.name }}</AuthorSpot>
  </div>

  <div class="mx-5 categories">
    <Button v-for="category in categories" 
      :large="true"
      :key="category.id" 
      :icon="category.icon" 
      :counter="category.size"
      @click="(e) => openCategory(category, e)">{{ category.name }}</Button>
  </div>
</template>

<style scoped>
.categories {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(20em, 1fr));
  gap: 1em;
}
.authors {
  gap: 1em;
  overflow-x: auto;
}
.authors::-webkit-scrollbar {
  display: none;
}
</style>
