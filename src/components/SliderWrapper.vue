<template>
  <div class="slider-wrapper">
    <ProgressBar :value="value" :maxValue="maxValue" class="progress-bar" />
    <div>
      <h4>Slider controller with props, events, watchers etc</h4>
      <SliderController
        :value="value"
        :maxValue="maxValue"
        @valueChange="value = $event"
        @maxValueChange="maxValue = $event"
      />
    </div>
    <div>
      <h4>Slider controller with v-models</h4>
      <SliderControllerVModels
        v-model:value="value"
        v-model:maxValue="maxValue"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import ProgressBar from './ProgressBar.vue';
import SliderController from './SliderController.vue';
import SliderControllerVModels from './SliderControllerVModels.vue';

const value = ref(0);
const maxValue = ref(20);
</script>
<style scoped>
.progress-bar {
  margin-bottom: 20px;
}

.slider-wrapper {
  text-align: center;
  padding: 20px;
  border: 2px solid red;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}
</style>
