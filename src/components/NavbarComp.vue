<template>
  <nav class="bg-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo Name -->
        <div class="flex-shrink-0 text-white text-lg md:text-3xl font-bold">
          CwetheinShop
        </div>

        <!-- Desktop Icons -->
        <div class="hidden md:flex space-x-6">
          <a href="#" class="text-gray-400 hover:text-white">
            <!-- Home Icon -->
            <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 9.5V7a2 2 0 012-2h14a2 2 0 012 2v2.5l-9 9-9-9z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v12.75" />
            </svg>
          </a>
          <a href="#" class="text-gray-400 hover:text-white">
            <!-- Shop Icon -->
            <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 7h18M16 21v-9M8 21v-9M21 7L12 2 3 7M12 2v19M3 12h18" />
            </svg>
          </a>
          <a href="#" class="text-gray-400 hover:text-white">
            <!-- About Icon -->
            <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5z" />
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5zM12 14v9m0 0l9-5m-9 5l-9-5" />
            </svg>
          </a>
          <a href="#" class="text-gray-400 hover:text-white">
            <!-- Contact Icon -->
            <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89-2.6a2 2 0 011.22 0L20 8M3 8v9.5A2.5 2.5 0 005.5 20h13a2.5 2.5 0 002.5-2.5V8m-17 0l7 3m-7 0l7 3m7-3l7 3m-7 0l7 3" />
            </svg>
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <div class="md:hidden flex items-center">
          <button @click="toggleMenu" class="text-gray-400 hover:text-white focus:outline-none">
            <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path v-if="!isOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
              <path v-if="isOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div v-if="isOpen" class="md:hidden">
      <div class="px-2 pt-2 pb-3 space-y-1 sm:px-3">
        <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md">
          <!-- Home Icon -->
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 9.5V7a2 2 0 012-2h14a2 2 0 012 2v2.5l-9 9-9-9z" />
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 3v12.75" />
          </svg>
        </a>
        <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md">
          <!-- Shop Icon -->
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 7h18M16 21v-9M8 21v-9M21 7L12 2 3 7M12 2v19M3 12h18" />
          </svg>
        </a>
        <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md">
          <!-- About Icon -->
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5 9 5z" />
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 14l9-5-9-5-9 5zM12 14v9m0 0l9-5m-9 5l-9-5" />
          </svg>
        </a>
        <a href="#" class="text-gray-300 hover:text-white block px-3 py-2 rounded-md">
          <!-- Contact Icon -->
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89-2.6a2 2 0 011.22 0L20 8M3 8v9.5A2.5 2.5 0 005.5 20h13a2.5 2.5 0 002.5-2.5V8m-17 0l7 3m-7 0l7 3m7-3l7 3m-7 0l7 3" />
          </svg>
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isOpen: false,
    };
  },
  methods: {
    toggleMenu() {
      this.isOpen = !this.isOpen;
    },
  },
};
</script>
