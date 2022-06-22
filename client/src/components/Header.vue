<script setup lang="ts">
import { ref } from "vue";
import router from "@/router"

const input = ref(null);

function goHome(e: any) { 
  router.push("/")
}
</script>

<template>
  <div class="d-flex flex-column align-items-center text-center px-5 py-5">
    <h1 class="mb-0 logo" @click="goHome">C++<b>Hub</b></h1>
    <div class="mb-4">Best lectures, articles and books on C++</div>
    <div class="w-100 d-flex flex-row justify-content-center">
      <div class="search d-flex flex-row flex-fill">
        <input class="flex-fill form-control" type="text" placeholder="What do you want to find?">
        <button type="button" class="btn btn-primary ms-2">Search</button>
      </div>
    </div>
  </div>

  <hr class="mx-5 mb-3" />
</template>

<style scoped>
.search {
  max-width: 600px;
}
.logo:hover {
  cursor: pointer;
}
</style>