<template>
  <nav class="bg-white bg-opacity-95 fixed top-0 left-0 right-0 z-50" :class="{ 'shadow-lg': isSticky, 'hidden': isHidden }">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex justify-between items-center h-16">
      <div class="flex items-center">
        <img src="~/assets/images/vp.png" alt="Logo" class="h-8 w-full">
      </div>
      <div class="hidden md:flex md:items-center space-x-4">
        <NavLink url="/" name="Home" />
        <NavLink url="#about" name="About" />
        <NavLink url="#pricing" name="Pricing" />
        <BaseButton url="http://venuepro.digipoint.biz/subscription" name="Sign Up"
          class="max-w-full px-8 py-4 bg-gradient-to-r from-[#468ef9] to-[#0c66ee] border border-[#0c66ee] text-white" />
        <BaseObutton url="http://venuepro.digipoint.biz/login" name="Log In"
          class="max-w-full px-6 py-4 bg-inherit text-gradient border border-[#0c66ee] flex items-center justify-center text-blue-700 hover:text-white" />
      </div>
      <div class="flex md:hidden items-center">
        <button @click="isNavOpen = !isNavOpen" class="text-blue-900 focus:outline-none">
          <svg class="h-6 w-6" :class="{ 'hidden': isNavOpen, 'block': !isNavOpen }" xmlns="http://www.w3.org/2000/svg"
            fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
          <svg class="h-6 w-6" :class="{ 'hidden': !isNavOpen, 'block': isNavOpen }" xmlns="http://www.w3.org/2000/svg"
            fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
    </div>
    <div class="md:hidden" :class="{ 'block': isNavOpen, 'hidden': !isNavOpen }">
      <div class="px-2 pt-2 pb-3 space-y-1 flex flex-col">
        <NavLink url="/" name="Home" />
        <NavLink url="/about" name="About" />
        <NavLink url="#pricing" name="Pricing" />
        <div class="flex justify-between">
          <BaseButton name="Sign Up"
            class="max-w-full px-8 py-4 bg-gradient-to-r from-[#468ef9] to-[#0c66ee] border border-[#0c66ee] text-white" url="/" />
          <BaseButton name="Log In" url="/" 
            class="max-w-full px-6 py-4 bg-inherit text-gradient border border-[#0c66ee] flex items-center justify-center text-blue-700 hover:text-white" />

        </div>
      </div>
    </div>
  </nav>
</template>

<script>
import NavLink from '@/components/NavLink.vue'
import BaseButton from '@/components/base/Button.vue'
import BaseObutton from '@/components/base/OButton.vue'

export default {
  components: {
    NavLink,
    BaseButton,
    BaseObutton
  },
  data() {
    if (typeof window !== 'undefined') {
  return {
      isNavOpen: false,
      isSticky: false,
      prevScrollPos: window.pageYOffset,
      isHidden: false,
      currentScrollPos: 0
    }
} else{
  return {
      isNavOpen: false,
      isSticky: false,
      prevScrollPos: 0,
      isHidden: false,
      currentScrollPos: 0
    }
}
    
  },
  mounted() {
    if (typeof window !== 'undefined') {
 window.addEventListener('scroll', this.handleScroll)
}
    
  },
  beforeDestroy() {
    if (typeof window !== 'undefined') {
   window.removeEventListener('scroll', this.handleScroll)
}
   
  },
  methods: {
    handleScroll() {
      const currentScrollPos = window.pageYOffset;
      if (currentScrollPos > this.prevScrollPos && currentScrollPos > 100) {
        // Scrolling down, hide navbar
        this.isSticky = false;
        this.isHidden = true;
      } else {
        // Scrolling up, show navbar
        this.isHidden = false;
        if (currentScrollPos <= 0) {
          // At the very top, remove the shadow
          this.isSticky = false;
        } else {
          // Not at the very top, add the shadow
          this.isSticky = true;
        }
      }
      this.prevScrollPos = currentScrollPos;
    },
    
  },
}

</script>

<style scoped>
nav {
  transition: all 0.3s ease-in-out;
}
</style>