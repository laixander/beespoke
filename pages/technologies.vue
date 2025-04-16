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
        <UContainer class="py-4 lg:py-20 space-y-20">
            <div class="grid grid-cols-1 lg:grid-cols-4 gap-y-10 gap-x-20">
                <Feature 
                    v-for="(feature, index) in items" 
                    :key="index" 
                    v-bind="feature"
                />
            </div>

            <div class="dark:bg-gray-900 p-20 space-y-20">
                <FancyHeading 
                    title="Why Choose Our Technology Stack?"
                    highlight="Our Technology"
                    align="center"
                />

                <div class="grid grid-cols-1 lg:grid-cols-3 gap-y-10 gap-x-20">
                    <Feature 
                        v-for="(feature, index) in reasons" 
                        :key="index" 
                        v-bind="feature"
                        align="center"
                    />
                </div>
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner, items, reasons } from '@/data/technologies'
</script>