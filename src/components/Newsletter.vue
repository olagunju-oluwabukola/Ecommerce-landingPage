<template>
    <div class="bg-gray-900 text-white">
      <div class="container mx-auto flex flex-col md:flex-row items-center justify-between">
        <img src="/images/unsplash_JM-qKEd1GMI.svg" alt="Shoe Image" class=" md:block w-48 md:w-56">
        <div class="md:w-1/2">
          <h2 class="text-2xl font-semibold mb-4 text-center md:text-left text-wrap">Subscribe to our Newsletter</h2>
          <form @submit.prevent="subscribe" class="flex flex-col md:flex-row m-4">
            <input type="email" placeholder="Enter your email" class="p-6  rounded-l-md  md:w-2/3 mb-4 md:mb-0">
            <button class="bg-purple-500 hover:bg-purple-600 text-white text-sm md:text-xl font-bold py-2 rounded-r-md">Subscribe</button>
          </form>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "NewsletterSection",
    methods: {
      subscribe() {
        alert("Thank you for subscribing!");
      },
    },
  };
  </script>
  

  