<script setup>
import { defineProps } from 'vue'
defineProps({
  value: String,
  maxValue: String
})
</script>
<template>
  <div class="progress-bar">
    <div
      class="progress-indicator"
      :style="{
        'background-color':
          Math.min(Math.round((value / maxValue) * 100), 100) === 100 ? 'green' : 'red',
        width: Math.min(Math.round((value / maxValue) * 100), 100) + '%'
      }"
    ></div>
  </div>
</template>

<style>
.progress-value {
  padding: 0.5rem;
  color: red;
  font-size: 3rem;
}
.progress-bar {
  width: 100%;
  height: 26px;
  background-color: rgb(210, 210, 210);
  border-radius: 10px;
  margin: 10px 0;
}
.progress-bar .progress-indicator {
  height: 20px;
  border-radius: 10px;
  margin: 3px 0;
}
</style>
