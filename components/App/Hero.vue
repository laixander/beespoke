<template>
    <section :class="heroConfig">
        <UContainer :class="wrapperConfig">
            <div class="space-y-24 w-full py-20 order-first">
                <div class="space-y-6">
                    <div class="font-bold text-balance text-5xl lg:text-7xl text-gray-800 dark:text-gray-100">
                        We’re
                        <span class="before:block before:absolute before:-inset-1 before:-skew-y-3 before:bg-primary-500 relative inline-block">
                            <span class="relative text-white">Enablers</span>
                        </span>
                        of Automation
                    </div>
                    <div class="font-extralight lg:text-2xl text-gray-500 dark:text-gray-400">
                        We Deliver Simple, Modern and Sustainable Digital Experiences.
                    </div>
                </div>
                <div class="lg:flex gap-2">
                    <UButton label="Talk to our expert" size="xl" color="black" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
                    <UButton label="Checkout our products" variant="ghost" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }">
                        <template #trailing>
                            <UIcon name="i-heroicons-arrow-right-20-solid" class="w-5 h-5" />
                        </template>
                    </UButton>
                </div>
            </div>
            <div class="flex justify-center lg:justify-end items-center order-last">
                <div class="flex gap-4">
                    <div class="pt-24 lg:pt-80">
                        <div class="bg-primary-200 dark:bg-primary-950 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-01.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                    <div class="space-y-5 pt-8 lg:pt-36">
                        <div class="bg-primary-200 dark:bg-primary-950 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-02.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                        <div class="bg-primary-200 dark:bg-primary-950 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-03.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                    <div class="space-y-5 gap-4 lg:pb-36">
                        <div class="bg-primary-200 dark:bg-primary-950 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-04.jpg" alt="" class="absolute object-cover object-left w-full h-full">
                        </div>
                        <div class="bg-primary-200 dark:bg-primary-950 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-05.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                </div>
            </div>
        </UContainer>
    </section>
</template>

<script setup lang="ts">
const heroConfig = 'bg-gradient-to-t from-primary-100 to-white dark:from-primary-950 overflow-hidden'
const wrapperConfig = 'lg:flex items-center lg:min-h-[calc(100vh-60px)] gap-8 py-4 lg:py-8'
</script>