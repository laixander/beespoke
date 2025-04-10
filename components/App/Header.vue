<template>
    <header :class="headerClass">
        <div class="w-full flex items-center gap-2">
            <UAvatar src="/logo.png" alt="Beespoke Solution Inc." size="lg" />
            <div class="font-light text-primary-500 dark:text-primary-400 w-full">
                Beespoke Solutions Inc.
            </div>
        </div>
        <UHorizontalNavigation :links="links" :ui="uiNavConfig" />
        <div class="w-full text-right">
            <ColorMode />
        </div>
    </header>
</template>

<script setup lang="ts">
const headerClass = 'flex justify-between items-center px-4 border-b border-gray-100 dark:border-gray-800'
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