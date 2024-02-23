<script setup>
import { computed, ref } from "vue";
import { gsap, Power2 } from "gsap";
const props = defineProps({
  item: {
    type: Object,
    required: true,
  },
  index: {
    type: Number,
    required: true,
  },
});

const number = computed(() => `${props.index + 1}`.padStart(2, "0"));
const $el = ref(null);

const onEnter = () => {
  gsap.killTweensOf($el.value);

  gsap.to($el.value, {
    paddingLeft: 0,
    duration: 0.335,
    ease: Power2.easeInOut,
  });
};
const onLeave = () => {
  gsap.killTweensOf($el.value);

  gsap.to($el.value, {
    paddingLeft: '8rem',
    duration: 0.335,
    ease: Power2.easeInOut,
  });
};
</script>

<template>
  <li class="border-b border-gray-400 cursor-pointer">
    <div
      ref="$el"
      @mouseenter="onEnter"
      @mouseleave="onLeave"
      class="pl-32 py-12 flex items-start space-x-8 relative z-20"
    >
      <span class="text-xs text-gray-500 translate-y-3">({{ number }})</span>
      <h3 class="text-6xl">{{ item.title }}</h3>
    </div>
  </li>
</template>
