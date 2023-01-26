<template>
  <nav
    id="navbar"
    class="bg-white border-gray-200 px-2 sm:px-4 dark:bg-gray-900"
  >
    <div
      class="container flex flex-wrap justify-between items-center mx-auto flex items-center"
    >
      <span
        id="nav-title"
        class="leading-none self-center text-2xl sm:text-4xl font-semibold whitespace-nowrap text-white md:text-5xl mt-1 mb-2"
        >Julian PASSEBECQ - 27 y.o</span>
       
      
      <div class="w-auto text-white py-2.5" id="navbar-buttons">
        <button
          @click="showReadme"
          class="nav-button text-sm sm:text-lg bg-white hover:bg-black hover:text-white text-black font-bold py-1 px-2 md:px-4 rounded inline-flex items-center mr-2.5"
        >
        <svg
        xmlns="http://www.w3.org/2000/svg"
        class="mr-1.5 nav-icon w-4 h-4 lg:w-6 lg:h-6"
        viewBox="0 0 24 24"
      >
        <path
          d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm0 18.25c-.69 0-1.25-.56-1.25-1.25s.56-1.25 1.25-1.25c.691 0 1.25.56 1.25 1.25s-.559 1.25-1.25 1.25zm1.961-5.928c-.904.975-.947 1.514-.935 2.178h-2.005c-.007-1.475.02-2.125 1.431-3.468.573-.544 1.025-.975.962-1.821-.058-.805-.73-1.226-1.365-1.226-.709 0-1.538.527-1.538 2.013h-2.01c0-2.4 1.409-3.95 3.59-3.95 1.036 0 1.942.339 2.55.955.57.578.865 1.372.854 2.298-.016 1.383-.857 2.291-1.534 3.021z"
        />
      </svg>
          
          <span class="mt-1">4 years EXP</span>
        </button>
        <a
          href="https://www.linkedin.com/in/julian-p95/"
          target="_blank"
          rel="noopener noreferrer"
        >
          <button
            class="nav-button text-sm sm:text-lg bg-white hover:bg-black hover:text-white text-black font-bold py-1 px-2 md:px-4 rounded inline-flex items-center"
          >

          <svg xmlns="http://www.w3.org/2000/svg" 
          
          class="mr-1.5 nav-icon w-4 h-4 lg:w-6 lg:h-6"
            viewBox="0 0 24 24">
          
          <path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
            <span class="mt-1">Linkedin</span>
            
            
            
          </button>
        </a>
        
      </div>
      
    </div>
  </nav>
</template>

<style>
@font-face {
  font-display: swap;
  
}



#nav-title {
  text-shadow: 1px 1px 0 #000, -1px -1px 0 #000, 1px -1px 0 #000,
    -1px 1px 0 #000, 1px 1px 0 #000;
  font-family: "Anvir", serif;
  font-size: 16px;
  
}
#navbar {
  background-color: #87ccfacd;
}
.nav-button:hover .nav-icon {
  fill: #ffffff;
}
</style>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  methods: {
    showReadme() {
      this.$emit("showReadme", true);
    },
  },
});
</script>
