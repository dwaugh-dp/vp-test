<template>
  <a :href="url" class="border border-blue-500 bg-blue-500 text-white hover:bg-blue-600 rounded-full py-2 px-4 md:py-3 md:px-6 transition duration-300">
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