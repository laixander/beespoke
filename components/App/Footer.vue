<template>
    <footer :class="footerConfig">
        <UContainer :ui="uiContainerConfig">
            <div class="space-y-4">
                <BeespokeLogo class="w-14 h-14" />
                <Feature
                    v-for="(feature, index) in brand" 
                    :key="index" 
                    v-bind="feature"
                />
            </div>
            <List :items="detailList" />
            <div class="space-y-2">
                <h4 class="font-medium text-gray-800 dark:text-gray-100">
                    Sitemap
                </h4>
                <UVerticalNavigation :links="links" :ui="uiNavConfig" />
            </div>
        </UContainer>
        <UContainer>
            <div class="mt-10 pt-4 border-t border-gray-200 dark:border-white/5 text-center">
                <span class="font-light text-sm text-gray-500">&copy;2025 <span class="text-primary-500">Beespoke Solutions Inc.</span> Made by Human</span>
            </div>
        </UContainer>
    </footer>
</template>

<script setup lang="ts">
import { computed } from 'vue'
import { brand, detailList } from '@/data/footer'
import { links } from '@/data/menu'

const props = defineProps<{
  gradient?: boolean
}>()

const footerConfig = computed(() => {
  const base = 'py-10 lg:py-20'
  const gradient = 'bg-gradient-to-t from-primary-100 to-white dark:from-primary-950'
  return props.gradient ? `${base} ${gradient}` : base
})

const uiContainerConfig = {
    base: 'grid grid-cols-1 lg:grid-cols-3 gap-8'
}

const uiNavConfig = {
    wrapper: 'border-s border-gray-200 dark:border-white/5',
    base: 'group flex border-s -ms-px leading-8 before:hidden',
    padding: 'p-0 ps-4',
    rounded: '',
    font: '',
    ring: '',
    active: 'text-primary-500 dark:text-primary-400 border-current',
    inactive: 'border-transparent hover:border-gray-400 dark:hover:border-gray-500 text-gray-700 hover:text-gray-900 dark:text-gray-400 dark:hover:text-gray-300',
    icon: {
        active: 'text-primary-500 dark:text-primary-400',
    },
}
</script>

<!-- <style scoped>
:deep(ul) {
    @apply space-y-2.5;
}
</style> -->