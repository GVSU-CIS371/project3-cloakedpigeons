<template>
  <div>
    <Beverage :isIced="currentTemp === 'Cold'" :beverage="currentBaseBev" :syrup="currentSyrup" :creamer="currentCreamer"/>
    <ul>
      <li>
        <b>Temperature:</b>
        <template v-for="temp in temps" :key="temp">
          <label>
            <input
              type="radio"
              name="temperature"
              :id="`r${temp}`"
              :value="temp"
              v-model="currentTemp"
            />
            {{ temp }}
          </label>
        </template>
      </li>
      <li>
        <b>Creamer:</b>
        <template v-for="creamer in creamers" :key="creamer">
          <label>
            <input
              type="radio"
              name="creamer"
              :id="`r${creamer}`"
              :value="creamer"
              v-model="currentCreamer"
            />
            {{ creamer }}
          </label>
        </template>
      </li>
      <li>
        <b>Syrup:</b>
        <template v-for="syrup in syrups" :key="syrup">
          <label>
            <input
              type="radio"
              name="syrup"
              :id="`r${syrup}`"
              :value="syrup"
              v-model="currentSyrup"
            />
            {{ syrup }}
          </label>
        </template>
      </li>
      <li>
        <b>Base Beverage:</b>
        <template v-for="baseBev in baseBevs" :key="baseBev">
          <label>
            <input
              type="radio"
              name="baseBev"
              :id="`r${baseBev}`"
              :value="baseBev"
              v-model="currentBaseBev"
            />
            {{ baseBev }}
          </label>
        </template>
      </li>
    </ul>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
import Beverage from "./components/Beverage.vue";
// Define reactive data
const temps = ref(["Hot", "Cold"]);
const creamers = ref(["None","Milk","Cream","Half & Half"]);
const syrups = ref(["None","Vanilla","Caramel","Hazelnut"]);
const baseBevs = ref(["Coffee","Green Tea","Black Tea"]);
const currentTemp = ref("Hot");
const currentCreamer = ref("None");
const currentSyrup = ref("None");
const currentBaseBev = ref("Coffee");
</script>

<style lang="scss">
body,
html {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background-color: #6e4228;
  background: linear-gradient(to bottom, #6e4228 0%, #956f5a 100%);
}
ul {
  list-style: none;
}
</style>