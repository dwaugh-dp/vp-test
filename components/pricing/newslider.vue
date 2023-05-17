<template>
    <div class="relative w-full h-5">
      <input
        class="absolute w-full h-full opacity-0 cursor-pointer"
        type="range"
        min="1"
        max="3"
        step="1"
        v-model="selectedValue"
      />
      <div class="bg-gray-300 h-px w-full rounded-full"></div>
      <div
        v-for="(label, index) in labels"
        :key="index"
        :class="labelClasses(index)"
        class="absolute top-2 text-xs font-medium text-gray-500"
        :style="{ left: `${index * 33.33}%` }"
        @click="selectedValue = index + 1"
        
      >
        {{ label }}
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        selectedValue: 1,
        labels: ["Up to 5 rooms", "Up to 10 rooms", "Up to 20 rooms"],
      };
    },
    methods: {
      labelClasses(index) {
        return [
          "cursor-pointer",
          index === this.selectedValue - 1 ? "text-blue-500" : "text-gray-500",
        ];
      },
    },
  };
  </script>
  <!-- empty code goes here -->