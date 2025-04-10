<template>
    <div class="bg-gradient-to-t from-primary-100 to-white dark:from-primary-950 overflow-hidden">
        <div class="container mx-auto lg:flex items-center lg:h-[calc(100vh-60px)] gap-8">
            <div class="space-y-24 w-full py-20 px-4 order-first">
                <div class="space-y-6">
                    <div class="font-semibold text-balance text-5xl lg:text-7xl text-gray-800 dark:text-gray-100">
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
                <div class="flex gap-2">
                    <UButton label="Talk to our expert" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
                    <UButton label="Checkout our products" variant="ghost" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }">
                        <template #trailing>
                            <UIcon name="i-heroicons-arrow-right-20-solid" class="w-5 h-5" />
                        </template>
                    </UButton>
                </div>
            </div>
            <div class="flex justify-center lg:justify-end items-center p-4 order-last">
                <div class="flex gap-4">
                    <div class="pt-24 lg:pt-80">
                        <div class="bg-primary-200 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-01.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                    <div class="space-y-5 pt-8 lg:pt-36">
                        <div class="bg-primary-200 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-02.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                        <div class="bg-primary-200 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-03.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                    <div class="space-y-5 gap-4 lg:pb-36">
                        <div class="bg-primary-200 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-04.jpg" alt="" class="absolute object-cover object-left w-full h-full">
                        </div>
                        <div class="bg-primary-200 relative w-44 h-64 rounded-lg overflow-hidden">
                            <img src="/photo-05.jpg" alt="" class="absolute object-cover w-full h-full">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>