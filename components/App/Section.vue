<template>
    <section :class="[sectionClass, isEven ? 'bg-gray-50 dark:bg-gray-900' : '']">
        <slot />
    </section>
</template>

<script setup lang="ts">
defineProps<{
    isEven?: boolean
}>()

const sectionClass = 'p-4'
</script>