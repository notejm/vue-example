<script setup lang="ts">
import { defineProps, ref, watch, watchEffect } from 'vue';
const props = defineProps<{
  value: number;
  maxValue: number;
}>();

const emit = defineEmits<{
  valueChange: [value: number];
  maxValueChange: [value: number];
}>();

const value = ref(props.value);
const maxValue = ref(props.maxValue);

watchEffect(() => {
  value.value = Math.min(props.value, props.maxValue);
  maxValue.value = props.maxValue;
});

watch(value, (newValue: number) => {
  emit('valueChange', newValue);
});

watch(maxValue, (newMaxValue: number) => {
  emit('maxValueChange', newMaxValue);
});
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
