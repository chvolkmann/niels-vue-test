<template>
  <div>XD?</div>
</template>

<script lang="ts">
export default {
  created() {
    console.log("CREATE");
  },
  mounted() {
    console.log("MOUNT1");

    console.log("MOUNT2");

    console.log("MOUNT3");
  },
  unmounted() {
    console.log("UNMOUNT");
  },
};
</script>
