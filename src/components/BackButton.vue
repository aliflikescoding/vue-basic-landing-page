<script setup>
import { RouterLink } from "vue-router";
</script>

<template>
  <section>
    <div class="container m-auto py-6 px-6">
      <RouterLink
        to="/jobs"
        class="text-green-500 hover:text-green-600 text-xl flex gap-2 items-center"
      >
        <i class="pi pi-arrow-circle-left"></i>
        <p>Back to Job Listings</p>
      </RouterLink>
    </div>
  </section>
</template>
