<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article v-for="(item, index) in banner" :key="index" :title="item.title" :highlight="item.highlight"
                    :paragraphs="item.paragraphs" />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>

        <!-- Inline Component: Articles with Images with Alternate Position-->
        <UContainer class="grid gap-16 py-4 lg:py-20">
            <div v-for="(item, index) in items" :key="index" class="grid lg:grid-cols-2 gap-8 items-center">
                <!-- Image -->
                <div :class="index % 2 === 1 ? 'lg:order-2' : ''" class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80">
                    <!-- <img :src="item.image" :alt="item.title" class="w-full rounded-xl shadow-md" /> -->
                </div>

                <!-- Article -->
                <div :class="index % 2 === 1 ? 'lg:order-1' : ''">
                    <Article :title="item.title" :paragraphs="item.paragraphs" size="text-2xl" hasDivider />
                </div>
            </div>
        </UContainer>
        
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner, items } from '@/data/products'
</script>