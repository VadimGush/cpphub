<script setup lang="ts">
const props = defineProps({
  thumbnailUrl: String,
  title: String,
  author: String,
  description: String,
  id: String,
});
</script>

<template>
  <router-link :to="{ name: 'item', params: { id } }" class="link">
    <article :key="id" class="result-card" @click="">
      <!-- TODO: Add alt text or disabled person will disable you! -->
      <div><img class="thumbnail" :src="thumbnailUrl" /></div>
      <div>
        <div class="title">{{ title }}</div>
        <div class="author">{{ author }}</div>
        <div class="description">{{ description }}</div>
      </div>
    </article>
  </router-link>
</template>

<style scoped>
.thumbnail {
  width: 20em;
  aspect-ratio: 16 / 9;
  object-fit: cover;
}
.author {
  margin-block-end: 1em;
  font-size: 1.1em;
}
.title {
  font-size: 1.5em;
}
.result-card {
  padding: 1rem;
  display: grid;
  grid-template-columns: minmax(0, auto) 2fr;
  column-gap: 1em;
}
.link {
  color: inherit;
  text-decoration: inherit;
}
</style>
