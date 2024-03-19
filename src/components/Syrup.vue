<template>
  <div class="syrup" :style="{ backgroundColor: syrupColor }"></div>
</template>

<script setup lang="ts">
import { computed } from "vue";
type Syrup = {
  name: string;
  color: string;
};
const Syrups: Syrup[] = [
  {
    name: "Vanilla",
    color: "#FFEFD5",
  },
  {
    name: "Caramel",
    color: "#DAA520",
  },
  {
    name: "Hazelnut",
    color: "#6B4423",
  },
];

// Update props to allow the base beverage to change
const props = defineProps({
  name: String,
});

// Function for base bev
const syrupColor = computed(() => {
  const selectedBase = Syrups.find(syrup => syrup.name === props.name);
  return selectedBase ? selectedBase.color : "";
});

</script>
<style lang="scss" scoped>
.syrup {
  transform: translateY(400%);
  position: relative;
  width: 100%;
  height: 20%;
  animation: pour-tea 2s 1s forwards;
  z-index: 2;
}
</style>
