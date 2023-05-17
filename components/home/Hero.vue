<template>
  <section id="about" class="w-full pb-4 pt-16 sm:pt-20 bg-white h-full" >
    <BaseSection>
      <div class="col-span-12 lg:col-span-6 mt-12 xl:mt-10 space-y-4 sm:space-y-6 px-6 text-center sm:text-left">
        <h1 class="text-[2.5rem] sm:text-5xl xl:text-6xl font-bold leading-tight capitalize sm:pr-8 xl:pr-10">
          Empowering <br><span class="text-header-gradient ">property managers</span> <br>
          to streamline operations
        </h1>
        <p class="text-lg paragraph hidden sm:block ">
          Take control of your physical meeting space management with a centralized hub for inventory and booking. Empower
          your teams to self-book spaces and view upcoming events visually with real-time digital signage.
        </p>
        <div class="flex flex-col sm:flex-row space-y-4 sm:space-y-0 sm:space-x-4 mt-2">
          <BaseButton name="Sign Up" url="/" 
            class="max-w-full px-8 py-4 bg-gradient-to-r from-[#468ef9] to-[#0c66ee] border border-[#0c66ee] text-white" />
          <BaseOButton name="Learn More" url="/" 
            class="max-w-full px-6 py-4 bg-inherit text-gradient border border-[#0c66ee] flex items-center justify-center text-blue-700 hover:text-white" />
        </div>
      </div>
      <div class="hidden sm:block col-span-12 lg:col-span-6 pt-16">
        <div class="w-full">
          <img src="~/assets/images/DASH.gif" class="-mt-4" alt="" />
        </div>
      </div>
    </BaseSection>
  </section>
</template>

<script>
import BaseSection from '~/components/base/Section.vue'
import BaseButton from '~/components/base/Button.vue'
import BaseOButton from '~/components/base/OButton.vue'

export default {
  name: 'HomeHero',
  components: {
    BaseSection,
    BaseButton,
    BaseOButton,
  },
}
</script>

<style scoped>
.text-header-gradient {
  background: rgb(57, 132, 244);
  background: linear-gradient(169.4deg, #3984f4 -6.01%, #8fd3f4 36.87%, #2f7cf0 78.04%, #0e65e8 103.77%);
  background-clip: text;
  -webkit-text-fill-color: transparent;


}

/* .highlight {
  background-image: linear-gradient(120deg, #84fab0 0%, #8fd3f4 100%);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
  padding: 2px 4px;
  border-radius: 12px;
} */
</style>


