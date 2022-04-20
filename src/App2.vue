<script setup>
import { Motion, Presence } from "motion/vue";
import { ref } from "vue";

const rotation = ref(45);
const show = ref(true);
</script>

<template>
  <button @click="rotation = Math.random() * 360">Rotate</button>
  <Motion
    class="box"
    :initial="false"
    :animate="{ rotate: rotation }"
    :transition="{ duration: 1, easing: 'ease-in-out' }"
  />
  <button @click="show = !show">Toggle</button>
  <Presence>
    <Motion
      v-if="show"
      class="box"
      :initial="{ opacity: 0, scale: 0 }"
      :animate="{ opacity: 1, scale: 1 }"
      :exit="{ opacity: 0, scale: 0 }"
      :transition="{ duration: 1, easing: 'ease-in-out' }"
    />
  </Presence>
</template>

<style>
.box {
  margin: 100px;
  width: 200px;
  height: 200px;
  background: #43b993;
  border-radius: 5px;
}
</style>
