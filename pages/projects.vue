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
        <!-- <ComingSoon /> -->
         <UContainer class="py-10 lg:py-20">
            <UTabs :items="items" :ui="uiTabsConfig">
                <template #projects>
                  <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
                        <FancyCard 
                            v-for="(card, i) in projects"
                            :key="i"
                            v-bind="card"
                            icon="i-lucide-building-2"
                        />
                    </div>
                </template>
                <template #clients>
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
                        <FancyCard 
                            v-for="(card, i) in clients"
                            :key="i"
                            v-bind="card"
                        />
                    </div>
                </template>
            </UTabs>
         </UContainer>
    </AppSection>
    <AppSection>
      <UContainer class="text-center py-10 lg:py-20">
            <FancyHeading 
                title="Ready to start your next project?"
                size="text-3xl"
            />
            <FancyDivider align="center" />
            <p class="prose mx-auto dark:text-gray-400 mb-8">
              Let's work together to bring your vision to life with innovative technology solutions designed for your specific needs.
            </p>
            <UButton label="Start a Project" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
import { banner, clients, projects } from '@/data/projects'

const items = [
    {
        slot: 'projects',
        label: 'Projects',
        icon: 'i-lucide-package-2'
    },
    {
        slot: 'clients',
        label: 'Clients',
        icon: 'i-lucide-user-round-check'
    }
]

const uiTabsConfig = {
    wrapper: 'space-y-10 flex flex-col justify-center w-full',
    list: { 
        base: 'mx-auto',
        rounded: 'rounded-full',
        height: 'h-13',
        width: 'w-auto',
        marker: {
            background: 'bg-primary dark:bg-primary-900',
            rounded: 'rounded-full',
        },
        tab: {
            active: 'text-white dark:text-white',
            height: 'h-11',
            padding: 'px-5',
            size: 'text-base',
            font: 'font-light',
            rounded: 'rounded-full',
            icon: 'w-5 h-5 me-3'
        }
    }
}

// const cards = [
//   {
//     image: '/bnr-propertytax.jpg',
//     tag: 'Dolores',
//     title: 'SmartJuan24',
//     description: 'Simplified public service platform built for accessibility and transparency.',
//     buttons: [
//       { label: 'Learn More', to: '/smartjuan' },
//       { label: 'Get Started', to: '/register' }
//     ]
//   },
//   {
//     title: 'Paperless Permits',
//     description: 'Apply for business permits online, fast and secure.',
//     buttons: [{ label: 'Apply Now', to: '/permits' }]
//   }
// ]
</script>