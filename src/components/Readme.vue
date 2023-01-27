<template>
  <vue-final-modal
    v-slot="{ params, close }"
    v-bind="$attrs"
    v-model="showModalModel"
    classes="flex justify-center items-center"
    content-class="relative flex flex-col max-h-full mx-4 p-4 border rounded bg-night-blue text-white"
    @closed="closed"
    :transition="{
      'enter-active-class': 'transition duration-350 ease-in-out transform',
      'enter-class': 'translate-y-full',
      'enter-to-class': 'translate-y-0',
      'leave-active-class': 'transition duration-350 ease-in-out transform',
      'leave-to-class': 'translate-y-full',
      'leave-class': 'translate-y-0',
    }"
  >
    <div
      class="flex-grow overflow-y-auto text-left sm: px-6 xl:px-32 max-w-lg lg:max-w-2xl xl:max-w-3xl 2xl:max-w-7xl"
    >
      <slot v-bind:params="params"></slot>
      <h1 v-if="isPrerender" class="text-3xl">
        Julian
      </h1>
      </div>
      <h2 class="text-2xl mt-8 font-bold text-white">CONTACT & CV</h2>
      <div class="ml-2 md:ml-4">
        
        <h3>
          Whatsapp :
          
            +33 7 67 42 48 98
          
        </h3>
        <h3>
          Email :
          
            julian.passebecq@gmail.com 
        </h3>
        <h3>
          CV : 
        </h3>
      </div>
      <h2 class="text-2xl mt-8 font-bold text-white">WORK EXP - 2017->2022</h2>
      <div class="ml-2 md:ml-4">
        
       
      </div>

      <h2 class="text-xl mt-6">- 2017: SAVENCIA, Data Intern</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          Automation tool on Excel/VBA with SAP Stock/Forecast BI PoC
          
        </h3>
        
      </div>

      <h2 class="text-xl mt-6">- 2018/19: TOTAL - Product Owner</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          Power BI PoC, A to Z + Oracle database
          
        </h3>
        
      </div>
      <h2 class="text-xl mt-6">- 2020/21: Startup - Data Engineer</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          Aquaponic farm simulation on Azure + ML
         
          
        </h3>
        
        <h2 class="text-xl mt-6">- 2022: Danone,Jr Digital Manager</h2>
        <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          7 Power BI Projects, Azure, Data Analytics
         
          
        </h3>
       
        
      </div>

      <h2 class="text-2xl mt-8 font-bold text-white">EDUCATION - 2012-2018</h2>
      <div class="ml-2 md:ml-4">
        
       
      </div>
      <h2 class="text-xl mt-6">- Bachelor Mathematics Informatics</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          France 2012-2014 , Database, SQL, R
          
        </h3>
        
      </div>
      <h2 class="text-xl mt-6">- Master of Science - Engineering</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          Major - Energy, Renewable, Optic Fiber
         
          
        </h3>
        
         <h3 class="mt-2">
          
          Minor - Big Data, Open Data, Analytics
          
        </h3>
        
        
      </div>
      
    </div>
    <button
      @click="closed"
      class="absolute top-0 right-2 mt-2 mr-2 text-2xl sm:text-base"
    >
      X
    </button>
  </vue-final-modal>
</template>

<script>
import { VueFinalModal, ModalsContainer } from "vue-final-modal";

export default {
  props: {
    showModal: {
      type: Boolean,
      required: true,
    },
    isPrerender: {
      type: Boolean,
      required: true,
    },
  },
  computed: {
    showModalModel: {
      get () {
        return this.showModal
      },
      set (value) {
        if (value === false) {
          this.closed()
        }
      }
    },
  },
  name: "Readme",
  components: {
    VueFinalModal,
    ModalsContainer,
  },
  methods: {
    closed() {
      this.$emit("close");
    },
  },
};
</script>
