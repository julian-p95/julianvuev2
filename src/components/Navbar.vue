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
        >Julian PASSEBECQ</span
      >
      <div class="w-auto text-white py-2.5" id="navbar-buttons">
        <button
          @click="showReadme"
          class="nav-button text-sm sm:text-lg bg-white hover:bg-black hover:text-white text-black font-bold py-1 px-2 md:px-4 rounded inline-flex items-center mr-2.5"
        >
          
          <span class="mt-1">4 YEARS EXP</span>
        </button>
        <a
          href="https://www.linkedin.com/in/julian-p95/"
          target="_blank"
          rel="noopener noreferrer"
        >
          <button
            class="nav-button text-sm sm:text-lg bg-white hover:bg-black hover:text-white text-black font-bold py-1 px-2 md:px-4 rounded inline-flex items-center"
          >
            
            
            <span class="mt-1">LINKEDIN</span>
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
