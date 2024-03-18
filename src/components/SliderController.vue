<script setup>
import { defineProps } from 'vue'
defineProps({
  value: String,
  maxValue: String,
  updateValue: Function,
  updateMaxValue: Function
})
</script>

<template>
  <span>Max Value: {{ maxValue }}</span>
  <input
    type="range"
    min="1"
    max="100"
    :value="maxValue"
    @input="(event) => updateMaxValue(event)"
  />
  <span>Value: {{ value }}</span>
  <input
    type="range"
    min="1"
    :max="maxValue"
    :value="value"
    @input="(event) => updateValue(event)"
  />
</template>

<style></style>
