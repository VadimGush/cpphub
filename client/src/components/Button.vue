<script setup lang="ts">
const props = defineProps({
  icon: String,
  counter: Number,
  large: Boolean
});

const emit = defineEmits(["click"])
</script>

<template>
  <button :class="{'btn-lg': large}" 
          class="btn btn-secondary text-start d-flex flex-row align-items-center"
          @click="(e) => emit('click', e)">
    <i v-if="icon" :class="icon" class="bi me-2"></i> <slot /> 
    <div class="flex-grow-1"></div> 
    <span v-if="counter != undefined" class="badge text-bg-light text-secondary">{{ counter }}</span>
  </button>
</template>