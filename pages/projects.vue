<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in projects"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UnderConstruction />
    </AppSection>
    <AppSection>
        <AppHighlight />
    </AppSection>
</template>

<script setup lang="ts">
const projects = [
    {
        title: 'Our Projects',
        highlight: 'Our',
        paragraphs: [
            '**Beespoke Solutions Inc.** takes pride in delivering impactful, future-ready digital projects across government, education, and enterprise sectors. Each project reflects our commitment to innovation, collaboration, and excellence—transforming ideas into intelligent solutions that drive meaningful progress.'
        ]
    },
]
</script>