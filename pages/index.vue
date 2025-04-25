<template>
    <AppHero />
    <AppSection>
        <AppHighlights />
    </AppSection>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-2 gap-12 py-10 lg:py-20">
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                v-for="(item, index) in about"
                :key="index"
                :title="item.title"
                :highlight="item.highlight"
                :paragraphs="item.paragraphs"
            />
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="py-10 lg:py-20 space-y-10 lg:space-y-16">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in approach"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-10 lg:gap-20">
                <Feature v-for="(feature, index) in items" :key="index" v-bind="feature" />
            </div>
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
import { about, approach, items } from '@/data/home'

definePageMeta({
  footerGradient: true
})
</script>