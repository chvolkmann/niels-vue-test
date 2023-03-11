<template>
  <div class="http-call-test">
    <MyInput color="green" />
    <MyInput color="blue" />
    <MyInput v-bind:color="currentColor" />
    <button v-on:click="handleColorChange">Change color</button>

    <MyInput :color="currentColor" />
    <button @click="handleColorChange">Change color</button>

    <!-- <input id="my-url-input" :value="sd" @input="handleInput" />

    <hr />

    <pre>
      {{ urlText }}
    </pre> -->
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import MyInput from "./MyInput.vue";

const currentColor = ref("red");
function handleColorChange() {
  currentColor.value = "purple";
}

// async function makeHTTPGetCall(url: string) {
//   const resp = await fetch(url);
//   return await resp.json();
// }

// function makeHttpGetCallSync(url: string) {
//   return fetch(url).then((resp) => resp.json());
// }

const urlText = ref("");
function handleInput(ev: any) {
  const val: string = ev.target.value;
  console.log("NEW STATE", val);
  urlText.value = val;

  // title.value = "XD";
}
</script>

<style>
.http-call-test {
  background: #ccc;
  min-height: 200px;
  padding: 5px;
}
#my-url-input {
  border: solid 1px black;
}

pre {
  background: #fcc;
  min-height: 100px;
  margin-top: 50px;
}
</style>
