<script setup>
import { ref } from "vue";
import { useEventListener } from "@vueuse/core";
const x = ref(0);
const y = ref(0);

useEventListener(window, "mousemove", (e) => {
  x.value = e.clientX;
  y.value = e.clientY;
});
</script>

<template>
  <div
    class="w-[30vw] h-[18vw] fixed top-0 left-0 z-10 bg-green-500 -translate-x-1/2 -translate-y-1/2 pointer-events-none"
    :style="{ top: `${y}px`, left: `${x}px` }"
  ></div>
</template>
