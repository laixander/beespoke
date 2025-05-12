<template>
    <div :class="['relative w-full pb-[56.25%] lg:pb-[26.25%] overflow-hidden', { 'shadow-none': !isLoading }]">
      <!-- Loading Spinner -->
      <div v-if="isLoading" class="absolute inset-0 flex items-center justify-center bg-primary-200 dark:bg-primary-950 z-10">
        <Loader />
      </div>
  
      <!-- Fallback Image if map fails to load -->
      <img
        v-if="loadFailed"
        src="/map.png"
        alt="Map location"
        class="absolute top-0 left-0 w-full h-full object-cover"
      />
  
      <!-- Google Map Embed -->
      <iframe
        v-show="!loadFailed"
        class="absolute top-0 left-0 w-full h-full"
        src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d3861.717672763683!2d121.01642375924682!3d14.558130921838783!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397c97daf02e46f%3A0xca28a24249260379!2sRufino%20Pacific%20Tower!5e0!3m2!1sen!2sph!4v1746777795510!5m2!1sen!2sph"
        style="border:0;"
        allowfullscreen="false"
        loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        @load="mapLoaded"
      ></iframe>
    </div>
  </template>
  
  <script setup lang="ts">
  import { ref, onMounted } from 'vue';
  
  const isLoading = ref(true);
  const loadFailed = ref(false);
  
  const mapLoaded = () => {
    isLoading.value = false;
  };
  
  // Timeout fallback: if map hasn't loaded in 5 seconds, show fallback image
  onMounted(() => {
    setTimeout(() => {
      if (isLoading.value) {
        loadFailed.value = true;
        isLoading.value = false;
      }
    }, 10000); // Adjust timeout as needed
  });
  </script>