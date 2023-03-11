<template>
  <div>{{ counter }}</div>
  <button @click="increment">Increment</button>
</template>

<script lang="ts">
import { ref } from "vue";

export default {
  setup() {
    // onMounted(() => {
    //   console.log("MOUNT 1");
    // });

    // onMounted(() => {
    //   console.log("MOUNT 2");
    // });

    // onMounted(() => {
    //   console.log("MOUNT 3");
    // });

    console.log("SETUP");

    const counter = ref(42);
    function increment() {
      console.log("INC");
      counter.value = counter.value + 1;
    }

    return {
      counter,
      increment,
    };
  },
};
</script>
