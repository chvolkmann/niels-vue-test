<template>
  <div>{{ myText }}</div>
  <button @click="doubleText">Increment</button>
</template>

<script lang="ts" setup>
import { ref } from "vue";

import { twice } from "@/helpers";

console.log("SETUP COMPOSITION");

const counter = ref(42);
function increment() {
  console.log("INC");
  counter.value = counter.value + 1;
}

const myText = ref("Hello");
function doubleText() {
  myText.value = twice(myText.value);
}
</script>
