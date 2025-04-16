<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in banner"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-y-10 gap-x-20">
                <Feature 
                    v-for="(feature, index) in items" 
                    :key="index" 
                    v-bind="feature"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner, items } from '@/data/services'
</script>