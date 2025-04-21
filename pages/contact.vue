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
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 lg:gap-8">
                <UCard>
                    <UForm :state="state" class="space-y-4">
                        <UFormGroup label="Full Name" name="name" size="xl">
                            <UInput />
                        </UFormGroup>
                        <UFormGroup label="Email Address" name="email" size="xl">
                            <UInput />
                        </UFormGroup>
                        <UFormGroup label="Message" name="message" size="xl">
                            <UTextarea resize :rows="8" />
                        </UFormGroup>
                        <UButton label="Send Message" size="xl" color="black" :ui="{ rounded: 'rounded-full' }">
                            <template #leading>
                                <UIcon name="i-lucide-send" class="w-5 h-5" />
                            </template>
                        </UButton>
                    </UForm>
                </UCard>
                
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

const state = reactive({
//...
})
</script>