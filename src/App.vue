<script setup>
import List from "./components/List/index.vue";
import Logo from "@/assets/images/logo.svg";

const items = [
  {
    title: "About",
    image: "http://",
  },
  {
    title: "Services",
    image: "http://",
  },
  {
    title: "Portfolio",
    image: "http://",
  },
  {
    title: "Pricing",
    image: "http://",
  },
  {
    title: "Contact",
    image: "http://",
  },
];
</script>

<template>
  <div class="h-screen" style="background-color: #f0f0f0">
    <img
      :src="Logo"
      :width="130"
      :height="auto"
      alt="Logo"
      class="mx-auto pt-9 z-20"
      style="opacity: 0.7"
    />
    <div class="px-10 pt-1">
        <List :items="items" />
    </div>
  </div>
</template>
