<template>
    <a :href="url" class="border border-blue-500 hover:border-blue-600 text-blue-500 hover:text-white rounded-full py-2 px-4 md:py-3 md:px-6 transition duration-300">
      {{ name }}
    </a>
  </template>
  <script>
  export default {
    props: {
      url: {
        type: String,
        required: true
      },
      name: {
        type: String,
        required: true
      }
    }
  }
  </script>
  <style scoped>
  a:hover {
    background-color: #0c66ee;
  }
  a:focus {
    outline: none;
  }
  </style>