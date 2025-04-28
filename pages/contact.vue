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
                <div class="grid gap-6 *:rounded-xl *:p-6 *:flex *:flex-col *:justify-center">
                    <div class="bg-primary-50 dark:bg-primary-950/50">
                        <FancyHeading title="Contact Information" size="text-xl" margin="mb-6" />
                        <ul class="space-y-1.5">
                            <li><UButton label="(632) 8538-5056" icon="i-lucide-phone" variant="link" size="xl" :padded="false" /></li>
                            <li><UButton label="admin@beespokedev.com" icon="i-lucide-mail" variant="link" size="xl" :padded="false" /></li>
                            <li><UButton label="Live Chat Available" icon="i-lucide-message-square" variant="link" size="xl" :padded="false" /></li>
                        </ul>
                    </div>
                    <div class="bg-gray-50 dark:bg-gray-900">
                        <FancyHeading title="Office Hours" size="text-xl" margin="mb-4" />
                        <ul class="font-light text-gray-500 dark:text-gray-400 space-y-1">
                            <li>Monday - Friday: 8:00 AM - 5:00 PM</li>
                            <li>Saturday: 8:00 AM - 12:00 PM</li>
                            <li>Sunday: Closed</li>
                        </ul>
                    </div>
                </div>
         </UContainer>
    </AppSection>
    <Map />
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner } from '@/data/contact'

const state = reactive({
//...
})
</script>