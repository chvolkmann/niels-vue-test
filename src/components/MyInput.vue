<template>
  <input :value="myText" @input="handleInput" />
  <div :style="{ color }">Color: {{ color }}</div>
  <!-- <div :style="{ color: color }">{{ myText }}</div> -->
</template>

<script lang="ts" setup>
import { ref } from "vue";

defineProps({
  color: String,
});

const myText = ref("");
function handleInput(ev: any) {
  myText.value = ev.target.value;
}
</script>

<style>
input {
  border: solid black 1px;
}
</style>
