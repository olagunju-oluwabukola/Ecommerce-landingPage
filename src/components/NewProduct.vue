
   <template>
    <div>
      <h2 class="text-2xl font-semibold p-2">New Product Collection</h2>
      
      <!-- Carousel Component -->
      <carousel-comp/>
  
      <!-- Additional content for New Product category -->
      <div class="mt-8">
        <p class="text-lg text-gray-700">
          Discover the latest arrivals in our New Product collection. Featuring the newest trends and designs.
        </p>
      </div>
    </div>
  </template>
  
  <script>
import CarouselComp from './CarouselComp.vue';
  export default {
   components:{
    CarouselComp
   }
  };
  </script>
  
  <style scoped>
  /* Add any specific styles for NewProduct.vue here */
  </style>
  