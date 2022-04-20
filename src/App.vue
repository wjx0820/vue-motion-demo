<script setup>
import { onMounted } from "vue";
import { animate, spring } from "motion";

onMounted(() => {
  const animation = animate(
    ".box",
    { scale: 1.5 },
    {
      duration: 1,
      easing: spring(),
      repeat: Infinity,
    }
  );
});
</script>

<template>
  <div class="box" />
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
