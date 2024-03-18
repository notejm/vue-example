<template>
  <div class="progress-bar" :class="{ completed: isCompleted }">
    <div class="progress-indicator" :style="style"></div>
  </div>
</template>

<script setup lang="ts">
import { defineProps, computed } from 'vue';

const props = defineProps<{
  value: number;
  maxValue: number;
}>();

const percentage = computed<number>(() => {
  return Math.min(Math.round((props.value / props.maxValue) * 100), 100);
});

const isCompleted = computed<boolean>(() => {
  return percentage.value === 100;
});

const style = computed<Record<string, string>>(() => {
  return { width: percentage.value + '%' };
});
</script>

<style scoped>
.progress-bar {
  width: 100%;
  height: 5px;
  background-color: rgb(210, 210, 210);
  border: 1px solid black;
}

.progress-bar .progress-indicator {
  height: 100%;
  background-color: dodgerblue;
}

.progress-bar.completed .progress-indicator {
  background-color: limegreen;
}
</style>
