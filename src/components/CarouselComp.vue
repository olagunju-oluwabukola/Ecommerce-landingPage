<template>
  <div class="container mx-auto py-6">
    <!-- Carousel Wrapper -->
    <div class="relative w-full overflow-hidden">
      <!-- Carousel Items -->
      <div
        ref="carousel"
        class="flex transition-transform duration-700 ease-in-out"
        :style="{ transform: `translateX(-${currentSlide * 100 / slidesPerView}%)` }"
      >
        <!-- Individual Slide -->
        <div
          v-for="(item, index) in items"
          :key="index"
          class="flex-shrink-0 w-full sm:w-1/2 lg:w-1/4"
        >
          <div class="p-4 text-center">
            <img :src=item.src alt="Product Image" class="w-48 h-48 mx-auto" />
            <p class="mt-2">{{ item.name }}</p>
            <p class="mt-1 font-semibold">{{ item.price }}</p>
          </div>
        </div>
      </div>

      <!-- Navigation Buttons -->
      <!-- <button
        class="absolute left-0 top-1/2 transform -translate-y-1/2 px-2 py-1 bg-gray-800 text-white rounded-full"
        @click="prevSlide"
      >
        Prev
      </button>
      <button
        class="absolute right-0 top-1/2 transform -translate-y-1/2 px-2 py-1 bg-gray-800 text-white rounded-full"
        @click="nextSlide"
      >
        Next
      </button> -->
    </div>
  </div>
</template>

<script>
import img1 from '/images/img1.png'
import img2 from '/images/img2.png'
import img3 from '/images/img3.png'
import img4 from '/images/img4.png'
import img5 from '/images/img5.png'
import img6 from '/images/img6.png'
import img7 from '/images/img7.png'
import img8 from '/images/img8.png'
import img9 from '/images/img9.png'

export default {
  data() {
    return {
      currentSlide: 0,
      slidesPerView: 4, // Default to 4 slides per view on large screens
      items: [
        { name: "Retro sneakers", price: "NGN 3000", src: img1},
        { name: "Retro sneakers", price: "NGN 3000", src: img2},
        { name: "Retro sneakers", price: "NGN 3000", src: img3},
        { name: "Retro sneakers", price: "NGN 3000", src: img4},
        { name: "Retro sneakers", price: "NGN 3000", src: img5},
        { name: "Retro sneakers", price: "NGN 3000", src: img6},
        { name: "Retro sneakers", price: "NGN 3000", src: img7},
        { name: "Retro sneakers", price: "NGN 3000", src: img8},
        { name: "Retro sneakers", price: "NGN 3000", src: img9},
       
      ],
      interval: null,
    };
  },
  mounted() {
    this.updateSlidesPerView();
    window.addEventListener("resize", this.updateSlidesPerView);
    this.startAutoSlide();
  },
  methods: {
    updateSlidesPerView() {
     
      if (window.innerWidth < 640) {
        this.slidesPerView = 1; 
      } else if (window.innerWidth < 1024) {
        this.slidesPerView = 2; 
      } else {
        this.slidesPerView = 4; 
      }
    },
    startAutoSlide() {
      this.interval = setInterval(() => {
        this.nextSlide();
      }, 3000); 
    },
    stopAutoSlide() {
      clearInterval(this.interval);
    },
    nextSlide() {
      const maxSlides = this.items.length - this.slidesPerView;
      this.currentSlide = (this.currentSlide + 1) % (maxSlides + 1);
    },
    prevSlide() {
      const maxSlides = this.items.length - this.slidesPerView;
      this.currentSlide = (this.currentSlide - 1 + maxSlides + 1) % (maxSlides + 1);
    },
  },
  beforeDestroy() {
    this.stopAutoSlide();
    window.removeEventListener("resize", this.updateSlidesPerView);
  },
};
</script>

<style scoped>
.carousel-slide {
  min-width: 100%;
}
</style>
