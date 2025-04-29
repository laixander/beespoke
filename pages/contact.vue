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
                            <li>
                                <UButton label="(632) 8538-5056" variant="link" size="xl" :padded="false">
                                    <template #leading>
                                        <UIcon name="i-lucide-phone" class="w-5 h-5" />
                                    </template>
                                </UButton>
                            </li>
                            <li>
                                <UButton label="admin@beespokedev.com" variant="link" size="xl" :padded="false">
                                    <template #leading>
                                        <UIcon name="i-lucide-mail" class="w-5 h-5" />
                                    </template>
                                </UButton>
                            </li>
                            <li>
                                <UButton label="Live Chat Available" variant="link" size="xl" :padded="false">
                                    <template #leading>
                                        <UIcon name="i-lucide-message-square" class="w-5 h-5" />
                                    </template>
                                </UButton>
                            </li>
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