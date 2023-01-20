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
        Pazbek
      </h1>
      
      <h2 class="text-2xl mt-8 font-bold text-mikado">EDUCATION</h2>
      <div class="ml-2 md:ml-4">
        
       
      </div>
      <h2 class="text-xl mt-6">- Bachelor Mathematics Informatics</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          France 2012-2014 , Database, SQL, R, Finance
          
        </h3>
        
      </div>
      <h2 class="text-xl mt-6">- Master of Science - Engineering</h2>
      <div class="ml-2 md:ml-4">
        <h3 class="mt-2">
          Major - Energy, Renewable, Electricity, Optic Fiber
         
          
        </h3>
        
         <h3 class="mt-2">
          
          Minor - Big Data, Open Data, Database
          
        </h3>
        
        
      </div>
      <h2 class="text-2xl mt-8 font-bold text-mikado">Contact</h2>
      <div class="ml-2 md:ml-4">
        
        <h3>
         You can contact me by Phone/Whatsapp
          <a
            href="https://www.linkedin.com/in/ju95/"
            class="no-underline hover:underline text-mikado"
            >+33 7 8</a
          >
          
        </h3>
        <h3>
          You can reach me by email
          <a
            href="https://www.linkedin.com/in/julian-p95/"
            class="no-underline hover:underline text-mikado"
            >julian.pam</a
          >.
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
