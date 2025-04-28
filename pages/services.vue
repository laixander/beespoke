<template>
    <AppBanner>
        <UContainer class="py-10 lg:py-20">
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
    </AppBanner>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-3 gap-y-10 gap-x-20 py-4 lg:py-20">
            <Feature 
                v-for="(feature, index) in items" 
                :key="index" 
                v-bind="feature"
                :class="index === items.length - 1 ? 'lg:col-start-2' : ''"
            /> -->
            <Feature 
                v-for="(feature, index) in items" 
                :key="index" 
                v-bind="feature"
            />
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="text-center py-10 lg:py-20">
            <FancyHeading 
                title="Ready to elevate your digital capabilities?"
                size="text-3xl"
            />
            <FancyDivider align="center" />
            <p class="prose mx-auto font-light dark:text-gray-400 mb-8">
                Let our expert team help you transform your organization with cutting-edge technology solutions tailored to your needs.
            </p>
            <UButton label="Schedule a Consultation" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
import { banner, items } from '@/data/services'
</script>