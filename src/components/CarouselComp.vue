<template>
  <div class="max-w-7xl mx-auto py-12">
    <!-- Product Carousel -->
    <div class="relative overflow-hidden">
      <div
        ref="carousel"
        class="flex transition-transform duration-500"
        :style="{ transform: `translateX(-${currentSlide * (100 / visibleItems)}%)` }"
      >
        <div
          v-for="(product, index) in products"
          :key="index"
          class="w-[calc(100%/4)] flex-shrink-0 bg-white  rounded-lg p-4 text-center"
        >
          <img
            :src="product.image"
            :alt="product.name"
            class="h-32 w-full object-contain mb-4"
          />
          <h3 class="text-sm text-gray-500">{{ product.name }}</h3>
          <p class="text-lg font-semibold">{{ product.price }}</p>
        </div>
      </div>
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
      products: [
        { name: "Retro sneakers", price: "NGN 3000", image: img1 },
        { name: "Retro sneakers", price: "NGN 3000", image: img2 },
        { name: "Retro sneakers", price: "NGN 3000", image: img3 },
        { name: "Retro sneakers", price: "NGN 3000", image: img4 },
        { name: "Retro sneakers", price: "NGN 3000", image: img5 },
        { name: "Retro sneakers", price: "NGN 3000", image: img6 },
        { name: "Retro sneakers", price: "NGN 3000", image: img7 },
        { name: "Retro sneakers", price: "NGN 3000", image: img8 },
        { name: "Retro sneakers", price: "NGN 3000", image: img9 },
      ],
      currentSlide: 0,
      visibleItems: 4,
      autoSlideInterval: null,
    };
  },
  mounted() {
    this.startAutoSlide();
    this.checkScreenSize();
    window.addEventListener("resize", this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener("resize", this.checkScreenSize);
    this.stopAutoSlide();
  },
  methods: {
    startAutoSlide() {
      this.autoSlideInterval = setInterval(() => {
        this.scrollRight();
      }, 3000); // Change every 3 seconds
    },
    stopAutoSlide() {
      clearInterval(this.autoSlideInterval);
    },
    scrollLeft() {
      if (this.currentSlide > 0) {
        this.currentSlide--;
      }
    },
    scrollRight() {
      if (this.currentSlide < this.products.length - this.visibleItems) {
        this.currentSlide++;
      } else {
        this.currentSlide = 0;
      }
    },
    checkScreenSize() {
      if (window.innerWidth < 768) {
        this.visibleItems = 2;
      } else if (window.innerWidth < 1024) {
        this.visibleItems = 2;
      } else if (window.innerWidth < 1280) {
        this.visibleItems = 3;
      } else {
        this.visibleItems = 4;
      }
    },
  },
};
</script>

<style scoped>
/* Add custom styles if needed */
</style>
