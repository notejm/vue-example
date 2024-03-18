<script setup>
import { ref } from 'vue'
import SliderValue from './SliderValue.vue'
import SliderController from './SliderController.vue'

const value = ref('0')
const maxValue = ref('20')
const updateValue = (event) => {
  value.value = event.target.value
}
const updateMaxValue = (event) => {
  maxValue.value = event.target.value
}
</script>
<template>
  <div class="slider-wrapper">
    <SliderValue :value="value" :maxValue="maxValue" />
    <SliderController
      :value="value"
      :maxValue="maxValue"
      :updateValue="updateValue"
      :updateMaxValue="updateMaxValue"
    />
  </div>
</template>

<style>
.slider-wrapper {
  display: grid;
}
</style>
