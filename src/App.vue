<script setup>
import SliderWrapper from './components/SliderWrapper.vue'
</script>

<template>
  <div id="app">
    <div class="wrapper">
      <SliderWrapper />
    </div>
  </div>
</template>

<style scoped>
#app {
  display: flex;
  width: 100vw;
  height: 100vh;
  justify-content: center;
  align-items: center;
}
.wrapper {
  text-align: center;
  padding: 20px;
  border: 2px solid red;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
}
.wrapper button {
  margin: 0 2px;
}
</style>
