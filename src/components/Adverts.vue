<template>
    <div class="md:flex justify-center items-center gap-6 bg-gray-200  p-6">
      
      <div class="bg-gray-900 text-white rounded-lg shadow-lg p-6 md:w-1/2 ">
        <h2 class="text-lg md:text-4xl font-bold mb-4">{{ currentProduct.name }}</h2>
        <h3 class="text-gray-400 mb-4 text-sm md:text-2xl">{{ currentProduct.category }}</h3>
        <p class="text-sm md:text-3xl mb-6">{{ currentProduct.description }}</p>
   
        <div class="flex space-x-2 mb-6">
          <span 
            v-for="(color, index) in products" 
            :key="index" 
            :style="{ backgroundColor: color.colorCode }" 
            @click="changeProduct(index)"
            class="w-6 md:w-10 h-6 md:h-10 rounded-full cursor-pointer hover:scale-110 transform transition-transform"></span>
        </div>
        
        <!-- Shop Button -->
        <button 
          @click="showModal = true"
          class="bg-purple-500 hover:bg-purple-600 md:text-xl text-white font-bold py-2 px-4 rounded
                 transition-colors duration-300">
          Shop Now
        </button>
      </div>
  
      <!-- Shoe Image -->
      <div class="ml-8 mt-5">
        <img :src="currentProduct.image" alt="Shoe Image" 
             class="w-48 transform hover:scale-110 transition-transform duration-500">
      </div>
  
      <!-- Popup Modal -->
      <div v-if="showModal" class="fixed inset-0 bg-black bg-opacity-50 flex justify-center items-center">
        <div class="bg-white rounded-lg shadow-lg p-6 w-96">
          <h2 class="text-lg font-bold mb-4">Complete Your Purchase</h2>
          <form @submit.prevent="completePurchase">
            <div class="mb-4">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
                Name on Card
              </label>
              <input v-model="form.name" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="name" type="text" placeholder="John Doe" required>
            </div>
            <div class="mb-4">
              <label class="block text-gray-700 text-sm font-bold mb-2" for="cardNumber">
                Card Number
              </label>
              <input v-model="form.cardNumber" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="cardNumber" type="text" placeholder="1234 5678 9012 3456" required>
            </div>
            <div class="flex mb-4">
              <div class="mr-2">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="expiry">
                  Expiry Date
                </label>
                <input v-model="form.expiry" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="expiry" type="text" placeholder="MM/YY" required>
              </div>
              <div class="ml-2">
                <label class="block text-gray-700 text-sm font-bold mb-2" for="cvc">
                  CVC
                </label>
                <input v-model="form.cvc" class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline" id="cvc" type="text" placeholder="CVC" required>
              </div>
            </div>
            <div class="flex items-center justify-between">
              <button class="bg-purple-500 hover:bg-purple-600 text-white font-bold py-2 px-4 rounded w-full transition-colors duration-300" type="submit">
                Pay Now
              </button>
            </div>
          </form>
          <button @click="showModal = false" class="mt-4 text-gray-500 hover:text-gray-700">Cancel</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
import img1 from '/images/img6.png'
import img2 from '/images/img7.png'
import img3 from '/images/img8.png'
import img4 from '/images/img9.png'

  export default {
    data() {
      return {
        showModal: false,
        form: {
          name: '',
          cardNumber: '',
          expiry: '',
          cvc: '',
        },
        currentProductIndex: 0,
        products: [
          {
            name: 'Airmax Blazer Jumbo - Red',
            category: 'High Fashion',
            description: 'The latest model of Airmax, perfect for modern streetwear enthusiasts.',
            image: img1,
            colorCode: '#FF0000',
          },
          {
            name: 'Airmax Blazer Jumbo - Gray',
            category: 'High Fashion',
            description: 'Sleek and stylish, the gray version is perfect for any occasion.',
            image: img2,
            colorCode: '#808080',
          },
          {
            name: 'Airmax Blazer Jumbo - Wheat',
            category: 'High Fashion',
            description: 'Inspired by the earth tones, this wheat color adds a natural touch.',
            image: img3,
            colorCode: '#F5DEB3',
          },
          {
            name: 'Airmax Blazer Jumbo - Indigo',
            category: 'High Fashion',
            description: 'Bold and unique, the indigo version stands out in any crowd.',
            image: img4,
            colorCode: '#4B0082',
          },
        ],
      };
    },
    computed: {
      currentProduct() {
        return this.products[this.currentProductIndex];
      },
    },
    methods: {
      changeProduct(index) {
        this.currentProductIndex = index;
      },
      completePurchase() {
        // Simulate payment processing
        setTimeout(() => {
          this.showModal = false;
          alert('Payment successful!');
          // Reset form fields
          this.form.name = '';
          this.form.cardNumber = '';
          this.form.expiry = '';
          this.form.cvc = '';
        }, 1000);
      },
    },
  };
  </script>
  
  <style scoped>
  /* Add any additional styling if needed */
  </style>
  