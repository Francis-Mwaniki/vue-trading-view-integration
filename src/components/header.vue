<template>
 <div class="" :class="{ 'dark-mode': isDarkMode }">
    <button @click="toggleMode" class="toggle-btn flex-row">
  
      <div class="icon-container">
      <svg  v-if="!isDarkMode"  xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" data-slot="icon" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M21.752 15.002A9.72 9.72 0 0 1 18 15.75c-5.385 0-9.75-4.365-9.75-9.75 0-1.33.266-2.597.748-3.752A9.753 9.753 0 0 0 3 11.25C3 16.635 7.365 21 12.75 21a9.753 9.753 0 0 0 9.002-5.998Z" />
</svg>
   
<svg v-else xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" data-slot="icon" class="w-6 h-6">
  <path stroke-linecap="round" stroke-linejoin="round" d="M12 3v2.25m6.364.386-1.591 1.591M21 12h-2.25m-.386 6.364-1.591-1.591M12 18.75V21m-4.773-4.227-1.591 1.591M5.25 12H3m4.227-4.773L5.636 5.636M15.75 12a3.75 3.75 0 1 1-7.5 0 3.75 3.75 0 0 1 7.5 0Z" />
</svg>

    </div>
    </button>
  </div>
  </template>
  
  <script>
  export default {
    components: {
    },
    data() {
      return {
        isDarkMode: false,
      };
    },
    methods: {
      toggleMode() {
        this.isDarkMode = !this.isDarkMode;
        document.documentElement.style.setProperty('--background-color', this.isDarkMode ? '#1f1f1f' : '#fff');
        document.documentElement.style.setProperty('--text-color', this.isDarkMode ? '#fff' : '#333');
        // Save mode preference (optional)
        localStorage.setItem('darkMode', this.isDarkMode);
      },
    },
    mounted() {
      // Check if mode preference is saved in local storage
      const savedMode = localStorage.getItem('darkMode');
      if (savedMode) {
        this.isDarkMode = savedMode === 'true'; // Convert string to boolean
        this.toggleMode(); // Apply saved mode
      }
    },
  };
  </script>
  
  <style scoped>
    

    .toggle-btn {
        padding: 0.5rem 1rem;
        border-radius: 0.5rem;
        border: none;
        display: flex;
        align-items: center;
        justify-content: center;
        justify-self: center;
        background-color: #fff;
        color: #333;
        font-size: 1rem;
        font-weight: bold;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    .toggle-btn:hover {
        background-color: #333;
        color: #fff;
    }

    .icon-container {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 100%;
        height: 100%;
    }

    .icon {
        width: 10rem;
        height: 10rem;
        transition: color 0.3s ease;
    }
    

    .w-6 {
        width: 1.5rem;
    }
    .h-6 {
        height: 1.5rem;
    }


@media (max-width: 768px) {
  .toggle-btn {
    padding: 0.5rem 1rem;
    border-radius: 0.5rem;
    border: none;
    display: flex;
    align-items: center;
    justify-content: center;
    justify-self: center;
    background-color: #fff;
    color: #333;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s ease;
}
.toggle-btn:hover {
    background-color: #333;
    color: #fff;

}

}
   
  </style>
  