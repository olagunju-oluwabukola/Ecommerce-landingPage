<template>
    <div class="max-w-7xl mx-auto py-12">
      
      <div class=" grid place-items-center md:flex justify-center space-x-8 border-b border-gray-200 pb-4">
        <button 
          v-for="(category, index) in categories" 
          :key="index" 
          @click="activeCategory = category" 
          :class="{'border-b-2 border-indigo-500 text-indigo-500': activeCategory === category}"
          class="px-4 p-2 text-sm md:text-2xl text-gray-600 focus:outline-none">
          {{ category }}
        </button>
      </div>
  
    
      <div class="relative mt-8 grid">
       
        <component :is="currentComponent" />
        

        <!-- <button 
          @click="scrollLeft" 
          class="absolute left-0 top-1/2 transform -translate-y-1/2 bg-white p-2 rounded-full shadow-md focus:outline-none"
        >
          <svg class="h-6 w-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
          </svg>
        </button>
        <button 
          @click="scrollRight" 
          class="absolute right-0 top-1/2 transform -translate-y-1/2 bg-white p-2 rounded-full shadow-md focus:outline-none"
        >
          <svg class="h-6 w-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
          </svg>
        </button> -->
      </div>
    </div>
  </template>
  
  <script>

  import NewProduct from './NewProduct.vue';
  import BestMatch from './BestMatch.vue';
  import Featured from './Featured.vue';
  
  export default {
    data() {
      return {
      
        activeCategory: 'New Product',
       
        categories: ['New Product', 'Best Match', 'Featured'],
       
        components: {
          'New Product': NewProduct,
          'Best Match': BestMatch,
          'Featured': Featured
        }
      };
    },
    computed: {
      
      currentComponent() {
        return this.components[this.activeCategory];
      }
    },
    methods: {
   
      scrollLeft() {
        this.$refs.carousel.scrollBy({ left: -200, behavior: 'smooth' });
      },
     
      scrollRight() {
        this.$refs.carousel.scrollBy({ left: 200, behavior: 'smooth' });
      }
    }
  };
  </script>
  