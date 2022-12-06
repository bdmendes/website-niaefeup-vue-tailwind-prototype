<script lang="ts">
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>

<template>
  <div class="text-center">
    <h1 class="text-4xl font-bold">&#60; {{ title }} /></h1>
  </div>
</template>
