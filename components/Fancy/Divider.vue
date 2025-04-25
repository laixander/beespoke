<template>
    <div :class="['w-full flex my-6 lg:my-8', alignmentClass]">
        <span class="w-20 h-1 bg-primary-500 rounded-full inline-block"></span>
    </div>
</template>

<script setup lang="ts">
const props = defineProps<{
    align?: 'left' | 'center' | 'right'
}>()

const alignmentClass = {
    left: 'justify-start',
    center: 'justify-center',
    right: 'justify-end'
}[props.align ?? 'left']
</script>


<!-- <template>
    <div class="*:h-1 *:bg-primary-500 *:rounded-full *:block space-y-1">
        <span class="w-8 animate-divider-scale" style="animation-delay: 0.3s"></span>
        <span class="w-20 animate-divider-scale" style="animation-delay: 0.1s"></span>
        <span class="w-16 animate-divider-scale" style="animation-delay: 0.2s"></span>
    </div>
</template>

<style scoped>
@keyframes scaleIn {
    0% {
        transform: scaleX(0);
        opacity: 0;
    }

    100% {
        transform: scaleX(1);
        opacity: 1;
    }
}

.animate-divider-scale {
    transform-origin: left;
    animation: scaleIn 0.4s ease-out forwards;
}
</style> -->