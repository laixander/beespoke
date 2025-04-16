<template>
    <AppHeader />
    <slot />
    <AppFooter :gradient="footerGradient" />
</template>

<script setup lang="ts">
const route = useRoute()
const footerGradient = computed(() => route.meta.footerGradient === true)
</script>