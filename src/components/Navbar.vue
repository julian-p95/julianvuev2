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
        >Julian PASSEBECQ</span>
       
      
      <div class="w-auto text-white py-2.5" id="navbar-buttons">
        <button
          @click="showReadme"
          class="nav-button text-sm sm:text-lg bg-white hover:bg-black hover:text-white text-black font-bold py-1 px-2 md:px-4 rounded inline-flex items-center mr-2.5"
        >
        <svg  xmlns="http://www.w3.org/2000/svg" class="mr-1 nav-icon w-4 h-4 lg:w-6 lg:h-6"
        viewBox="0 0 24 24"> >
        
        <path d="M3 24h19v-23h-1v22h-18v1zm17-24h-18v22h18v-22zm-3 17h-12v1h12v-1zm0-3h-12v1h12v-1zm0-3h-12v1h12v-1zm-7.348-3.863l.948.3c-.145.529-.387.922-.725 1.178-.338.257-.767.385-1.287.385-.643 0-1.171-.22-1.585-.659-.414-.439-.621-1.04-.621-1.802 0-.806.208-1.432.624-1.878.416-.446.963-.669 1.642-.669.592 0 1.073.175 1.443.525.221.207.386.505.496.892l-.968.231c-.057-.251-.177-.449-.358-.594-.182-.146-.403-.218-.663-.218-.359 0-.65.129-.874.386-.223.258-.335.675-.335 1.252 0 .613.11 1.049.331 1.308.22.26.506.39.858.39.26 0 .484-.082.671-.248.187-.165.322-.425.403-.779zm3.023 1.78l-1.731-4.842h1.06l1.226 3.584 1.186-3.584h1.037l-1.734 4.842h-1.044z"/>
      </svg>
          
          <span class="mt-1">4YR EXP</span>
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
          
          class="mr-1 nav-icon w-4 h-4 lg:w-6 lg:h-6"
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
