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
                <template #client>
                    <div class="grid grid-cols-1 lg:grid-cols-3 gap-10">
                        <FancyCard 
                            v-for="(card, i) in cards"
                            :key="i"
                            v-bind="card"
                        />
                    </div>
                </template>
                <template #internal>
                    Internal Projects
                </template>
            </UTabs>
         </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlights />
    </AppSection>
</template>

<script setup lang="ts">
import { banner } from '@/data/projects'

const items = [{
  slot: 'client',
  label: 'Client Projects',
  icon: 'i-lucide-user-round'
}, {
  slot: 'internal',
  label: 'Internal Projects',
  icon: 'i-lucide-building-2'
}]

const uiTabsConfig = {
    wrapper: 'space-y-8 flex flex-col justify-center w-full',
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

const cards = [
  {
    image: '/bnr-propertytax.jpg',
    tag: 'Dolores',
    title: 'SmartJuan24',
    description: 'Simplified public service platform built for accessibility and transparency.',
    buttons: [
      { label: 'Learn More', to: '/smartjuan' },
      { label: 'Get Started', to: '/register' }
    ]
  },
  {
    image: '/bnr-propertytax.jpg',
    tag: 'Dolores',
    title: 'SmartJuan24',
    description: 'Simplified public service platform built for accessibility and transparency.',
    buttons: [
      { label: 'Learn More', to: '/smartjuan' },
      { label: 'Get Started', to: '/register' }
    ]
  },
  {
    image: '/bnr-propertytax.jpg',
    tag: 'Dolores',
    title: 'SmartJuan24',
    description: 'Simplified public service platform built for accessibility and transparency.',
    buttons: [
      { label: 'Learn More', to: '/smartjuan' },
      { label: 'Get Started', to: '/register' }
    ]
  },
]
</script>