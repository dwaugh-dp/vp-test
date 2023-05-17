<template>
  <div class="rounded-lg overflow-hidden bg-blue-300 bg-opacity-10">
    <div class="px-12 ">
      <div class="relative h-0 pb-[50%] items-center justify-center" >
        <iframe class="absolute top-0 left-0 w-full h-full border border-gray-300 shadow-2xl rounded-3xl lg:mt-20 dark:border-gray-700 yt-video"
          :src="src"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen>
        </iframe>
      </div>
    </div>
  </div>
</template>
  
<script>
export default {
  props: {
    src: {
      type: String,
      required: true,
    },
  },
};
</script>
  
<style scoped>
div {
  aspect-ratio: 16/9;
  max-width: 100%;
}
iframe {
  width: 100%;
  height: 100%;
}
</style>
