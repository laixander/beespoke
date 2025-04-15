<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in contact"
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
const contact = [
    {
        title: 'Contact Us',
        highlight: 'Us',
        paragraphs: [
            'Let’s build something great together. Whether you’re looking to start a project, explore a partnership, or simply learn more about our solutions, the Beespoke team is ready to connect. Reach out today—we’re here to help you move forward with confidence.'
        ]
    },
]
</script>