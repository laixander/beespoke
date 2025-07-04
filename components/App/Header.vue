<template>
    <header :class="[baseClass, { 'bg-white/80 backdrop-blur dark:bg-gray-900/80': isScrolled }]">
        <div class="w-full flex items-center gap-2">
            <BeespokeLogo class="w-10 h-10" />
            <!-- <UAvatar src="/logo.png" alt="Beespoke Solutions Inc." size="md" /> -->
            <span class="text-primary-500 dark:text-primary-400 hidden xl:inline">
                Beespoke Solutions Inc.
            </span>
        </div>

        <div class="w-full flex justify-end items-center gap-2">
            <!-- Desktop Navigation -->
            <div class="hidden lg:block">
                <UHorizontalNavigation :links="links" 
                    :ui="{
                        wrapper: 'w-auto',
                        base: 'py-5 px-4',
                        after: 'after:h-[4px]'
                    }" 
                />
            </div>

            <div class="w-[1px] h-8 bg-gray-100 dark:bg-gray-800 mx-4 hidden lg:block"></div>
            <!-- Dark Mode Toggle (Always visible) -->
            <ColorMode />

            <div class="w-[1px] h-8 bg-gray-100 dark:bg-gray-800 mx-4 lg:hidden"></div>

            <!-- Mobile Menu Button -->
            <div class="lg:hidden">
                <UButton square variant="ghost" icon="i-heroicons-bars-3-16-solid" @click="isOpen = true" />
                <UModal v-model="isOpen" :ui="uiModalConfig">
                    <div class="px-4">
                        <UVerticalNavigation :links="links" @click="isClick" 
                            :ui="uiNavConfig" 
                        />
                    </div>
                </UModal>
                <!-- <USlideover v-model="isOpen">
                    <div class="p-4 flex-1">
                        <UVerticalNavigation :links="links" />
                    </div>
                </USlideover> -->
            </div>
        </div>
    </header>
</template>

<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import BeespokeLogo from '../BeespokeLogo.vue'
import { links } from '@/data/menu'

const isOpen = ref(false)
const isScrolled = ref(false)

const handleScroll = () => {
  isScrolled.value = window.scrollY > 0
}

// Close modal on screen resize to large breakpoint
const handleResize = () => {
  if (window.matchMedia('(min-width: 1024px)').matches) {
    isOpen.value = false
  }
}

// Close modal when a nav link is clicked
const isClick = () => {
  isOpen.value = false
}

onMounted(() => {
  handleScroll() // ← ensure the scroll state is set on initial load
  window.addEventListener('scroll', handleScroll, { passive: true })
  window.addEventListener('resize', handleResize)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
  window.removeEventListener('resize', handleResize)
})

const baseClass = 'sticky top-0 z-10 flex justify-between items-center px-4 py-2.5 lg:py-0 border-b border-gray-100 dark:border-gray-800 transition-[background-color,color] duration-300'
const uiNavConfig = {
    wrapper: 'border-s border-gray-200 dark:border-gray-800',
    base: 'group flex border-s -ms-px leading-6 before:hidden my-4',
    padding: 'p-0 ps-4',
    rounded: '',
    font: '',
    ring: '',
    active: 'text-primary-500 dark:text-primary-400 border-current',
    inactive: 'border-transparent hover:border-gray-400 dark:hover:border-gray-500 text-gray-400 hover:text-gray-900 dark:text-gray-400 dark:hover:text-gray-300',
    icon: {
        active: 'text-primary-500 dark:text-primary-400',
    },
}
const uiModalConfig = {
    container: 'flex min-h-full items-start sm:items-start justify-center text-center',
    margin: 'sm:m-4',
    width: 'w-full sm:max-w-full',
    transition: {
        enter: 'ease-out duration-300',
        enterFrom: 'opacity-0 -translate-y-6 sm:-translate-y-6 sm:scale-100',
        enterTo: 'opacity-100 translate-y-0',
        leave: 'ease-in duration-200',
        leaveFrom: 'opacity-100 translate-y-0',
        leaveTo: 'opacity-0 -translate-y-6 sm:-translate-y-6 sm:scale-100'
    }
}
</script>