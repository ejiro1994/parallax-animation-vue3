<script setup>
import ListItem from "./ListItem.vue";
defineProps({ items: { type: Array, required: true } });
import ListBox from "./listBox.vue";
</script>

<template>
  <ul>
    <ListItem
      :key="item.title"
      v-for="(item, index) in items"
      :item="item"
      :index="index"
    />
  </ul>

  <ListBox />
</template>
