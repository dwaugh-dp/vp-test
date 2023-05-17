<template>
  <a
    class="px-3 py-2 text-sm md:px-4 md:py-2 md:text-base bg-transparent rounded-lg text-[#666666] hover:text-gray-900 focus:outline-none focus:shadow-outline"
    :href="url"
  >
    {{ name }}
  </a>
</template>
<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
    },
    url: {
      type: String,
      required: true,
    },
  },
}
</script>