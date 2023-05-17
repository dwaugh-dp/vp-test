<template>
    <div class="container">
      <section class="photographer bg-red-600 hover:flex-2 transition-all duration-500">
        <h1 class="bg-black bg-opacity-60 text-white px-4 py-2">Photographer</h1>
      </section>
      <section class="designer bg-yellow-400 hover:flex-2 transition-all duration-500">
        <h1 class="bg-black bg-opacity-60 text-white px-4 py-2">Designer</h1>
      </section>
      <section class="developer bg-green-500 hover:flex-2 transition-all duration-500">
        <h1 class="bg-black bg-opacity-60 text-white px-4 py-2">Developer</h1>
      </section>
    </div>
  </template>
  
  <script>
  export default {
    mounted() {
      const sections = document.querySelectorAll("section");
  
      sections.forEach((section) => {
        section.addEventListener("mouseover", () => {
          section.classList.add("hover:flex-2");
        });
  
        section.addEventListener("mouseout", () => {
          section.classList.remove("hover:flex-2");
        });
      });
    },
  };
  </script>
  
  <style scoped>
  .container {
    display: flex;
    height: 100vh;
  }
  
  section {
    align-items: center;
    display: flex;
    flex: 1;
    justify-content: center;
  }
  
  section h1 {
    padding: 12px 32px;
  }
  
  .photographer {
    background-image: url("https://picsum.photos/id/1015/800/600");
    background-blend-mode: multiply;
  }
  
  .designer {
    background-image: url("https://picsum.photos/id/1021/800/600");
    background-blend-mode: multiply;
  }
  
  .developer {
    background-image: url("https://picsum.photos/id/1025/800/600");
    background-blend-mode: multiply;
  }
  </style>
  