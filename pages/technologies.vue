<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in techs"
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
const techs = [
    {
        title: 'Our Technologies',
        highlight: 'Our',
        paragraphs: [
            '**At Beespoke Solutions Inc.**, we harness modern web frameworks, container orchestration tools, and cloud-native databases to build reliable and scalable digital solutions. Our development approach emphasizes performance, flexibility, and long-term maintainability—ensuring your systems are ready for the demands of today and the innovations of tomorrow.'
        ]
    },
]
</script>