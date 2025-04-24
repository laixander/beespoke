<template>
    <AppBanner>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article v-for="(item, index) in banner" :key="index" :title="item.title" :highlight="item.highlight"
                    :paragraphs="item.paragraphs" />
            </div>
        </UContainer>
    </AppBanner>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-3 gap-10 py-4 lg:py-20">
            <Feature 
                v-for="(feature, index) in items" 
                :key="index" 
                v-bind="feature"
                unstyled
                iconSize="w-14 h-14"
            />
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="text-center py-4 lg:py-20">
            <FancyHeading 
                title="Why Choose Our Technology Stack?"
                align="center"
                size="text-3xl"
            />
            <FancyDivider align="center" class="mb-10" />
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
                <UCard 
                    v-for="(feature, index) in reasons" 
                    :key="index" 
                    :ui="{background: 'dark:bg-gray-950/30'}"
                >
                    <Feature 
                        v-bind="feature"
                        align="center"
                    />
                </UCard>
            </div>
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
import { banner, items, reasons } from '@/data/technologies'
</script>