<template>
    <div class="container m-auto p-8">
      <div class="grid gap-10 sm:grid-cols-2 md:grid-cols-3">
        <div 
          v-for="product in products" 
          :key="product.id" 
          class="bg-white rounded-lg shadow-lg overflow-hidden transform hover:scale-105 transition-transform duration-300"
        >
          <img :src="product.image" alt="Product Image" class="w-full h-56 object-cover">
          <div class="p-4">
            <h3 class="text-gray-700 font-semibold text-lg mb-2">{{ product.name }}</h3>
            <p class="text-purple-600 font-bold text-xl mb-2">{{ product.price }}</p>
            <button class="w-full bg-purple-500 hover:bg-purple-600 text-white font-bold py-2 px-4 rounded transition-colors duration-300">
              Add to cart
            </button>
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
          {
            id: 1,
            name: 'Jordan 1 Retro Royal sneakers',
            price: 'NGN 25,000',
            image: img1,
          },
          {
            id: 2,
            name: 'Jordan 4 sneakers',
            price: 'NGN 28,000',
            image: img2,
          },
          {
            id: 3,
            name: 'Brown and White Royal sneakers',
            price: 'NGN 45,000',
            image: img3,
          },
          {
            id: 4,
            name: 'Jordan Air sneakers',
            price: 'NGN 34,000',
            image: img4,
          },
          {
            id: 5,
            name: 'Jordan 5 sneakers',
            price: 'NGN 23,000',
            image: img5
          },
          {
            id: 6,
            name: 'Jordan 6 sneakers',
            price: 'NGN 31,000',
            image: img6,
          },
          {
            id: 7,
            name: 'Jordan 6 sneakers',
            price: 'NGN 24,000',
            image: img7,
          },
          {
            id: 8,
            name: 'Jordan 6 sneakers',
            price: 'NGN 22,000',
            image: img8,
          },
          {
            id: 9,
            name: 'Jordan 6 sneakers',
            price: 'NGN 32,000',
            image: img9,
          },
        ],
      };
    },
  };
  </script>
  
 
  