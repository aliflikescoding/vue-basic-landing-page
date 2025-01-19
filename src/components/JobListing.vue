<script setup>
import { defineProps, ref, computed } from "vue";

const props = defineProps({
  job: {
    type: Object,
  },
});

const showFullDesc = ref(false);

const toggleFullDesc = () => {
  showFullDesc.value = !showFullDesc.value;
};

const truncatedDescription = computed(() => {
  let description = props.job.description;
  if (!showFullDesc.value) {
    description = description.substring(0, 90) + "...";
  }
  return description;
});
</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <div class="text-gray-600 my-2">{{ job.type }}</div>
        <h3 class="text-xl font-bold">{{ job.title }}</h3>
      </div>

      <div class="mb-5">
        <div>
          {{ truncatedDescription }}
        </div>
        <button @click="toggleFullDesc" class="text-green-500 hover:underline hover:text-green-600 mt-2 mb-5">Show {{ showFullDesc ? 'Less' : 'More' }}</button>
      </div>

      <h3 class="text-green-500 mb-2">{{ job.salary }}</h3>

      <div class="border border-gray-100 mb-5"></div>

      <div class="flex flex-col lg:flex-row justify-between mb-4">
        <div class="text-orange-700 flex items-center gap-1">
          <i class="pi pi-map-marker text-orange-700"></i>
          <p>{{ job.location }}</p>
        </div>
        <a
          :href="`/job/${job.id}`"
          class="h-[36px] bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg text-center text-sm"
        >
          Read More
        </a>
      </div>
    </div>
  </div>
</template>
