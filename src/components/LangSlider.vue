<template>
  <div class="my-12">

    <div class="titl">
     
      
  </div>
    
    
    <hr class="border1" style="width:100%;align:center; margin-top: -3em;color:white">
    <div class="tit">
      
      <h1 class="tit0"></h1>
    </div>

    <div id="lang-wrapper">
      <swiper
      :grabCursor="true"
        :slideToClickedSlide="true"
        :centeredSlides="true"
        :modules="modules"
        :navigation="true"
        :slides-per-view="5"
        :loop="true"
        :breakpoints="{
          '1280': {
            slidesPerView: 8,
          },
        }"
      >
        <swiper-slide
        class="px-2 !mx-0 single-category"
        v-for="(cat, index) in catsFirstLine"
        :key="index"
        >
        <img
        @click="clickCategory(cat)"
        :class="`cursor-pointer max-h-16 category-img max-w-16 sm:max-h-18 sm:max-w-18 md:max-h-20 md:max-w-20 lg:max-h-24 lg:max-w-24 xl:max-h-28 xl:max-w-28 lang-logo
         ${cat.indexOf(' ') > -1?cat.replace(/ /g, '-'):cat }-logo`"
        :alt="cat"
        :src="`/logos/${cat}.png`"
      />
      <p class="category-name">{{ cat.split(' ').map(capitalize).join(' ') }}</p>
        </swiper-slide>
      </swiper>
    </div> 
    <div id="swiper-buttons" class="flex justify-between mb-4 mt-4 mx-4">
      <button>
        <svg @click="prev(0)"
          class="prev w-12 fill-gray hover:fill-mikado"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path d="M16 8v-4l8 8-8 8v-4h-16l8-8h8z" />
        </svg>
      </button>
      <button>
        <svg @click="next(0)"
          class="w-12 fill-gray hover:fill-mikado"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path d="M16 8v-4l8 8-8 8v-4h-16l8-8h8z" />
        </svg>
      </button>
    </div>

    <h1 class="data_heading"></h1>

    <div id="lang-wrapper">
      <swiper
      :grabCursor="true"
        :slideToClickedSlide="true"
        :centeredSlides="true"
        :modules="modules"
        :navigation="true"
        :slides-per-view="5"
        :loop="true"
        :breakpoints="{
          '1280': {
            slidesPerView: 8,
          },
        }"
      >
        <swiper-slide
        class="px-2 !mx-0 single-category"
        v-for="(cat, index) in catsSecondLine"
        :key="index"
        >
        <img
        @click="clickCategory(cat)"
        :class="`cursor-pointer max-h-16 mt-10 category-img max-w-16 sm:max-h-18 sm:max-w-18 md:max-h-20 md:max-w-20 lg:max-h-24 lg:max-w-24 xl:max-h-28 xl:max-w-28 lang-logo 
        ${cat.indexOf(' ') > -1?cat.replace(/ /g, '-'):cat }-logo`"
        :alt="cat"
        :src="`/logos/${cat}.png`"
      />
      <p class="category-name">{{ cat.split(' ').map(capitalize).join(' ') }}</p>
        </swiper-slide>
      </swiper>
    </div> 
    <div id="swiper-buttons" class="flex justify-between mt-4 mx-4">
      <button>
        <svg @click="prev(1)"
          class="prev w-12 fill-gray hover:fill-mikado"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path d="M16 8v-4l8 8-8 8v-4h-16l8-8h8z" />
        </svg>
      </button>
      <button>
        <svg  @click="next(1)"
          class="w-12 fill-gray hover:fill-mikado"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
        >
          <path d="M16 8v-4l8 8-8 8v-4h-16l8-8h8z" />
        </svg>
      </button>
    </div>
    
  </div>
  <hr class="border2" style="width:100%;align:center; margin-top: -3em;margin-bottom: 2.5em;color:white">
</template>

<style>



hr.border1 {
border-top: 0.5px dashed rgb(255, 255, 255);
}

hr.border2 {
  border-top: 0.5px dashed rgb(255, 255, 255);
  }
  




.data_heading {
  font-size: 16px;
  margin-top: -20px;
  margin-bottom: 0px;
  color: #fff;
  text-decoration: underline;
}

.title1 {
  font-size: 10px;
  margin-top: -20px;
  margin-bottom: 0px;
  text-align: center;
  color: #fff;
  margin-left: 3px;

}



.tit0 {
  font-size: 13px;
  margin-top: 10px;
  margin-bottom: 0px; 
  text-align: center;
  color: #fff;
  text-decoration: underline;
  
  
 
}
.title2 {
  font-size: 10px;
  margin-top: -20px;
  margin-bottom: 0px;
  text-align: center;
  color: #fff;
  margin-right: 3px;
  
 
}


#lang-wrapper {
  mask-image: linear-gradient(
    to right,
    transparent,
    #0c173c 5%,
    #0c173c 95%,
    transparent 100%
  );
}
.swiper-slide {
  display: flex;
  align-items: center;
  justify-content: center;
  align-self: center;
}
.swiper-button-prev,
.swiper-button-next {
  display: none;
}
.prev {
  transform: rotate(180deg);
}

@media all and (max-width: 640px) {
  #swiper-buttons {
    display: flex;
    justify-content: space-between;
  }
}
.lang-logo {
  opacity: 0.5;
}
.lang-logo:hover {
  opacity: 1;
}
.logo-selected {
  opacity: 1;
}


.swiper-slide.single-category {
  display: flex;
  flex-direction: column;
}

.single-category p.category-name {
  color: wheat;
  font-size: 10px;
}



div#swiper-buttons button svg {
  height: 15px;
}

</style>

<script lang="ts">
import { defineComponent } from "vue";
import { Swiper, SwiperSlide } from "swiper/vue";
import { Keyboard, FreeMode, Navigation } from "swiper";

// Import Swiper styles
import "swiper/css";

const CATEGORIESFIRSTLINE = [
  "python",
  "power bi",
  "ms azure",
  
  "R Stats",
  
  "Big Data",
  "Auto ML", 
  "SQL ddb",
  "Excel VBA",
  "Cloud Docker"
  
];
const CATEGORIESSECONDLINE = [
  "Supply",
  "Oil Gas",
  
  "Renewable",  
  "Electric",
  "Finance",
  "Efficiency",
  "Agriculture",
  "Marketing"
];

function highlightSelected(cat: string) {
  if(cat!="" && cat!='all') {
  const logos = document.querySelectorAll(".lang-logo");
  logos.forEach((logo) => {
    logo.classList.remove("logo-selected");
  });
  console.log("logo changed ",cat)
  document.querySelectorAll(`.${cat}-logo`).forEach((logo) => {
    logo.classList.add("logo-selected");
  });
}
else{
  const logos = document.querySelectorAll(".lang-logo");
  logos.forEach((logo) => {
    logo.classList.add("logo-selected");
  });
}
}

export default defineComponent({
  components: {
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      catsFirstLine: CATEGORIESFIRSTLINE,
      catsSecondLine: CATEGORIESSECONDLINE,
      modules: [Keyboard, Navigation, FreeMode],
    };
  },
  methods: {
    capitalize(str: string) {
      return str.charAt(0).toUpperCase() + str.slice(1).toLowerCase();
    },
    clickCategory(cat: string) {
      this.$emit("clickCategory", cat);
      if (cat.indexOf(" ") > -1) {
                highlightSelected(cat.replace(/ /g, "-"));
            } else
            highlightSelected(cat);
    },
    next(index: number) {
      let button = document?.getElementsByClassName(
        "swiper-button-next"
      )[index] as HTMLElement;
      console.log("button: " ,button);
      button.click();
    },
    prev(index: number) {
      let button = document?.getElementsByClassName(
        "swiper-button-prev"
      )[index] as HTMLElement;
      button.click();
    },
  },
  mounted() {
    highlightSelected("all");
  },
});
</script>
