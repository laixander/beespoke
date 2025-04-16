<template>
    <section :class="bannerConfig">
        <slot />
    </section>
</template>

<script setup lang="ts">
const bannerConfig = 'bg-gradient-to-t from-primary-100 to-white dark:from-primary-950 overflow-hidden'
</script>