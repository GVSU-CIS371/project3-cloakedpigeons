<template>
  <div class="baseBeverage" :style="{ backgroundColor: baseColor }"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
type BaseBeverage = {
  name: string;
  color: string;
};
const Bases: BaseBeverage[] = [
  {
    name: "Black Tea",
    color: "#8B4513",
  },
  {
    name: "Green Tea",
    color: "#C8E6C9",
  },
  {
    name: "Coffee",
    color: "#6F4E37",
  },
];

// Update props to allow the base beverage to change
const props = defineProps({
  name: String,
});

// Function for base bev
const baseColor = computed(() => {
  const selectedBase = Bases.find(base => base.name === props.name);
  return selectedBase ? selectedBase.color : "";
});
</script>

<style scoped>
.baseBeverage {
  position: relative;
  width: 100%;
  height: 100%;
  bottom: 0;
  animation: pour-tea 2s;
  z-index: 300;
  /* // border-radius: 0.05em 0.05em 2.2em 2.2em; */
}
</style>