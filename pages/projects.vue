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
        <UnderConstruction />
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner } from '@/data/projects'
</script>