<template>
  <!-- <router-view /> -->
  <div>loading: {{ loading }}</div>
  <div>resp:{{ response }}</div>
  <div>{{ counter }}</div>
  <button @click="handleClick">Click me</button>
</template>

<script lang="ts">
import { twice } from "@/helpers";

async function delay(ms: number) {
  return new Promise((resolve, reject) => setTimeout(resolve, ms));
}

async function fetchRequest(url: string) {
  await delay(1000);
  return {
    data: "XD",
  };
}

export default {
  data: () => ({
    loading: false,
    response: null,
    counter: 0,
  }),
  methods: {
    increment() {
      this.counter = this.counter + 1;
    },
    handleClick() {
      this.loading = true;
      const prom = fetchRequest("tagesschau.de");

      prom
        .then((resp) => {
          console.log("Response received!", resp);
          this.response = resp;
        })
        .catch((err) => console.error("ERROR", err))
        .finally(() => {
          this.loading = false;
        });

      console.log("XD");
      console.log(twice("XD"));
    },
  },
};
</script>
