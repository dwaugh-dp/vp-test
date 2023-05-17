<template>
    <Navbar />
    <div class="flex">
      <div
        class="w-1/2 bg-blue-900 h-screen flex flex-col items-center justify-center half-section"
        @mouseenter="expandSection(0)"
        @mouseleave="resetSection(0)"
        ref="section0"
      >
        <h1 class="text-white text-6xl text-center mb-8">MODULE A</h1>
        <button
          class="text-white py-3 px-6 bg-blue-500 rounded-lg hover:bg-blue-600 focus:outline-none"
         
        >
        Learn more
        </button>
      </div>
      <div
        class="w-1/2 bg-white h-screen flex flex-col items-center justify-center half-section"
        @mouseenter="expandSection(1)"
        @mouseleave="resetSection(1)"
        ref="section1"
      >
        <h1 class="text-gray-900 text-6xl text-center mb-8">MODULE B</h1>
        <button
          class="text-gray-900 py-3 px-6 bg-gray-200 rounded-lg hover:bg-gray-300 focus:outline-none"

        >
          Learn more
        </button>
      </div>
    </div>
  </template>
  
  <script>
    export default {
        methods: {
        expandSection(section) {
            const sectionRef = this.$refs[`section${section}`];
            sectionRef.classList.add("w-11/12");
            sectionRef.classList.remove("w-1/2");
        },
        resetSection(section) {
            const sectionRef = this.$refs[`section${section}`];
            sectionRef.classList.add("w-1/2");
            sectionRef.classList.remove("w-11/12");
        },
        },
    };
  </script>
  
  <style>
  .half-section {
    transition: width 0.7s ease-in-out;
  }
  </style>
  