<template>
  <div class="flex items-center">
    <button
      :class="{ 'bg-blue-500 text-white': selected === 'monthly', 'bg-gray-200 text-gray-500': selected !== 'monthly' }"
      class="mr-2 py-2 px-4 rounded-l-lg outline-none focus:outline-none" @click="select('monthly')">
      Monthly
    </button>
    <button
      :class="{ 'bg-blue-500 text-white': selected === 'annually', 'bg-gray-200 text-gray-500': selected !== 'annually' }"
      class="py-2 px-4 rounded-r-lg outline-none focus:outline-none" @click="select('annually')">
      Annually
    </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: 'annually'
    }
  },
  methods: {
    select(value) {
      this.selected = value;
      this.$emit('value-changed', value);
    }
  }
}
</script>
