<template>
    <header :class="[baseClass, { 'bg-white/80 backdrop-blur dark:bg-gray-900/80': isScrolled }]">
        <div class="w-full flex items-center gap-2">
            <UAvatar src="/logo.png" alt="Beespoke Solutions Inc." size="md" />
            <span class="text-primary-500 dark:text-primary-400">
                Beespoke Solutions Inc.
            </span>
        </div>
        <div class="w-full flex justify-end items-center gap-2">
            <UHorizontalNavigation :links="links" :ui="uiNavConfig" />
            <ColorMode />
        </div>
    </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})

const baseClass = 'sticky top-0 z-10 flex justify-between items-center px-4 border-b border-gray-100 dark:border-gray-800 transition-[background-color,color] duration-300'
const uiNavConfig = {
    wrapper: 'w-auto',
    base: 'py-5 px-4',
    after: 'after:h-[4px]'
}

const links = [
    {
        label: 'Home',
        icon: 'i-heroicons-home',
        to: '/'
    },
    {
        label: 'Services',
        icon: 'i-heroicons-cog-8-tooth',
        to: '/services'
    },
    {
        label: 'Products',
        icon: 'i-heroicons-cube',
        to: '/products'
    },
    {
        label: 'technologies',
        icon: 'i-heroicons-cpu-chip',
        to: '/technologies'
    },
    {
        label: 'Projects',
        icon: 'i-heroicons-rocket-launch',
        to: '/projects'
    },
    {
        label: 'Contact',
        icon: 'i-heroicons-device-phone-mobile',
        to: '/contact'
    }
]
</script>