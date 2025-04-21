<template>
    <div :class="['relative w-full pb-[56.25%] overflow-hidden', { 'rounded-lg shadow-lg': !isLoading }]">
        <!-- Loading Spinner -->
        <div v-if="isLoading" class="absolute inset-0 flex items-center justify-center bg-white dark:bg-gray-900 z-10">
            <Loader />
        </div>

        <!-- Google Map Embed -->
        <iframe class="absolute top-0 left-0 w-full h-full"
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d1930.1338458882262!2d121.01674635803198!3d14.55621982434462!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3397c9a4ad5a62ef%3A0xc2765d4370d6f7d4!2sRufino%20Pacific%20Tower%2C%2021st%20Floor%2C%20678%20Ayala%20Ave%2C%20Legazpi%20Village%2C%20Makati%2C%201220%20Metro%20Manila!5e0!3m2!1sen!2sph!4v1712800573432!5m2!1sen!2sph"
            style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"
            @load="mapLoaded"></iframe>
    </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// State to control loading state
const isLoading = ref(true);

// Method to handle map loading completion
const mapLoaded = () => {
    isLoading.value = false;
}
</script>