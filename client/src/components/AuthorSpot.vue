<script setup lang="ts">
const props = defineProps({
  picture: String,
});

const emit = defineEmits(["click"]);
</script>

<template>
  <div class="text-center author p-1" @click="(e) => emit('click', e)">
    <img :src="picture" />
    <div><slot /></div>
  </div>
</template>

<style scoped>
.author {
  min-width: 110px;
  line-height: 1.1em;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.75);
  background-color: rgba(0, 0, 0, 0);
  transition: 0.25s;
  border-radius: 0.5rem;
}
.author:hover {
  cursor: pointer;
}
.author:hover img {
  border: 4px solid #0d6efd;
}
.author img {
  transition: 0.25s;
  border: 4px solid rgba(0, 0, 0, 0.1);
  max-width: 70px;
  max-height: 70px;
  border-radius: 100%;
  margin-bottom: 7px;
}
</style>
