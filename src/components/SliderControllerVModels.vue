<script setup lang="ts">
import { defineModel, watch } from 'vue';
const value = defineModel('value', { type: Number, required: true, default: 0 });
const maxValue = defineModel('maxValue', { type: Number, required: true, default: 0 });

watch(
  () => maxValue.value,
  () => {
    value.value = Math.min(value.value, maxValue.value);
  },
  { immediate: true }
);
</script>

<template>
  <div class="slider-controller">
    <span>Max Value: {{ maxValue }}</span>
    <input type="range" min="1" max="100" v-model.number="maxValue" />
    <span>Value: {{ value }}</span>
    <input type="range" min="0" :max="maxValue" v-model.number="value" />
  </div>
</template>

<style scoped>
.slider-controller {
  display: grid;
}
</style>
