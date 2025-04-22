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
        <!-- <UnderConstruction /> -->
         <UContainer class="py-4 lg:py-20 space-y-20">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 lg:gap-10">
                <ContactForm />
                <Map />
            </div>
         </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner } from '@/data/contact'
import ContactForm from '~/components/ContactForm.vue';

const state = reactive({
//...
})
</script>