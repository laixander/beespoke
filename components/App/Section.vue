<template>
    <section ref="sectionRef" :class="[baseClass, isEven ? evenBg : '']">
        <slot />
    </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue'

const sectionRef = ref<HTMLElement | null>(null)
const isEven = ref(false)

const baseClass = 'transition-colors duration-300'
const evenBg = 'bg-gray-50 dark:bg-gray-900'

onMounted(() => {
    if (!sectionRef.value) return

    const sections = Array.from(document.querySelectorAll('section'))
    const index = sections.indexOf(sectionRef.value)
    isEven.value = index % 2 === 0
})
</script>