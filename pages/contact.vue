<template>
    <AppBanner>
        <UContainer class="py-10 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article v-for="(item, index) in banner" :key="index" :title="item.title" :highlight="item.highlight"
                    :paragraphs="item.paragraphs" />
            </div>
        </UContainer>
    </AppBanner>
    <AppSection>
        <!-- <UnderConstruction /> -->
         <UContainer class="grid grid-cols-1 lg:grid-cols-2 gap-6 lg:gap-10 py-10 lg:py-20">
                <ContactForm />
                <Map />
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