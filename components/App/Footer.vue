<template>
    <footer class="p-4">
        <div :class="wrapperClass">
            <div class="space-y-2 prose">
                <UAvatar src="/logo.png" alt="Beespoke Solutions Inc." size="md" />
                <h4 class="text-primary-500 dark:text-primary-400">Beespoke Solutions Inc.</h4>
                <p class="font-light text-sm text-gray-500 dark:text-gray-400 text-balance">
                    We Deliver Simple, Modern and Sustainable Digital Experiences.
                </p>
            </div>
            <FList :items="detailList" />
            <div class="space-y-2">
                <h4 class="font-medium text-gray-800 dark:text-gray-100">
                    Sitemap
                </h4>
                <UVerticalNavigation :links="links" :ui="uiNavConfig" />
            </div>
        </div>
    </footer>
</template>

<script setup lang="ts">
const wrapperClass = 'container mx-auto grid grid-cols-3 gap-8 py-10'
const uiNavConfig = {
    wrapper: 'border-s border-gray-200 dark:border-gray-800 space-y-2',
    base: 'group block border-s -ms-px leading-6 before:hidden',
    padding: 'p-0 ps-4',
    rounded: '',
    font: '',
    ring: '',
    active: 'text-primary-500 dark:text-primary-400 border-current font-semibold',
    inactive: 'border-transparent hover:border-gray-400 dark:hover:border-gray-500 text-gray-700 hover:text-gray-900 dark:text-gray-400 dark:hover:text-gray-300'
}

const links = [{
  label: 'Home',
to: '/'
}, {
  label: 'Services',
  to: '/services'
}, {
  label: 'Products',
  to: '/products'
}, {
  label: 'technologies',
  to: '/technologies'
}, {
  label: 'Projects',
  to: '/projects'
}, {
  label: 'Contact',
  to: '/contact'
}]

const detailList = [
  { icon: 'i-lucide-building', title: 'Find us at the office', description: 'L24 Philippine Stock Exchange Tower One Bonifacio High Street, 5th Ave. cor 28th St. BGC, Taguig City, Philippines 1634' },
  { icon: 'i-lucide-mail', title: 'Connect with us', description: 'ccci@centralizedinc.com' },
  { icon: 'i-lucide-phone', title: 'Give us a ring', description: '(632) 8538-5056' },
]
</script>

<style scoped>
:deep(ul) {
    @apply space-y-2.5;
}
</style>