<template>
    <div v-html="rendered" class="prose max-w-none font-light dark:prose-invert text-gray-500 dark:text-gray-400" />
</template>

<script setup lang="ts">
import { marked } from 'marked'

const props = defineProps<{ text: string }>()
const rendered = computed(() => marked(props.text || ''))
</script>