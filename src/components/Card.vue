<script setup>
import { defineProps } from "vue";

defineProps({
  bg: {
    type: String,
    default: "gray",
  },
  colorWeight: {
    type: String,
    default: "100"
  }
});
</script>

<template>
  <div :class="`bg-${bg}-${colorWeight} p-6 rounded-lg shadow-md`">
    <slot> </slot>
  </div>
</template>
