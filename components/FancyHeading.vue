<template>
    <h3 v-if="title" :class="[
        'font-semibold text-4xl text-gray-800 dark:text-gray-100 lg:mb-8',
        alignClass
    ]">
        <template v-if="highlight && title.includes(highlight)">
            <span v-if="before">{{ before }}</span>
            <span
                class="before:block before:absolute before:-inset-1 before:-skew-y-3 before:bg-primary-500 relative inline-block mx-1">
                <span class="relative text-white">{{ highlight }}</span>
            </span>
            <span v-if="after">{{ after }}</span>
        </template>
        <template v-else>
            {{ title }}
        </template>
    </h3>
</template>

<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
    title?: string
    highlight?: string
    align?: 'left' | 'center' | 'right'
}>()

const before = computed(() => {
    if (!props.title || !props.highlight) return ''
    const index = props.title.indexOf(props.highlight)
    return index !== -1 ? props.title.slice(0, index) : props.title
})

const after = computed(() => {
    if (!props.title || !props.highlight) return ''
    const index = props.title.indexOf(props.highlight)
    return index !== -1 ? props.title.slice(index + props.highlight.length) : ''
})

const alignClass = computed(() => {
    switch (props.align) {
        case 'center':
            return 'text-center'
        case 'right':
            return 'text-right'
        default:
            return ''
    }
})
</script>