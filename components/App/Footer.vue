<template>
    <footer :class="footerConfig">
        <UContainer :class="wrapperConfig">
            <div class="space-y-2 prose max-w-none">
                <UAvatar src="/logo.png" alt="Beespoke Solutions Inc." size="2xl" />
                <h3 class="text-primary-500 dark:text-primary-400">Beespoke Solutions Inc.</h3>
                <p class="font-light text-sm text-gray-500 dark:text-gray-400 text-balance">
                    We Deliver Simple, Modern and Sustainable Digital Experiences.
                </p>
            </div>
            <List :items="detailList" />
            <div class="space-y-2">
                <h4 class="font-medium text-gray-800 dark:text-gray-100">
                    Sitemap
                </h4>
                <UVerticalNavigation :links="links" :ui="uiNavConfig" />
            </div>
        </UContainer>
    </footer>
</template>

<script setup lang="ts">
const footerConfig = 'py-4 lg:py-20 bg-gradient-to-t from-primary-100 to-white dark:from-primary-950'
const wrapperConfig = 'container mx-auto grid grid-cols-1 lg:grid-cols-3 gap-8'
const uiNavConfig = {
    wrapper: 'border-s border-gray-200 dark:border-white/5',
    base: 'group block border-s -ms-px leading-6 before:hidden',
    padding: 'p-0 ps-4',
    rounded: '',
    font: '',
    ring: '',
    active: 'text-primary-500 dark:text-primary-400 border-current',
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
  { icon: 'i-lucide-mail', title: 'Connect with us', description: 'admin@beespokedev.com' },
  { icon: 'i-lucide-phone', title: 'Give us a ring', description: '(632) 8538-5056' },
]
</script>

<style scoped>
:deep(ul) {
    @apply space-y-2.5;
}
</style>