<template>
    <div class="flex flex-col items-start gap-4 lg:gap-6">
        <div v-if="icon" class="p-4 bg-primary-500 rounded-full inline-block">
            <UIcon :name="icon" class="w-6 h-6 text-white flex" />
        </div>
        <div class="prose max-w-none mb-auto">
            <h4 v-if="title" class="font-semibold text-xl text-gray-800 dark:text-gray-100">
                {{ title }}
            </h4>
            <p v-if="description" class="font-light text-gray-500 dark:text-gray-400">
                {{ description }}
            </p>
        </div>
        <UButton v-if="button" variant="link" :label="button" icon="i-lucide-arrow-right" :trailing="true"
            :padded="false" @click="$emit('cta')" />
    </div>
</template>

<script setup lang="ts">
defineProps<{
    icon?: string
    title?: string
    description?: string
    button?: string
}>()

defineEmits<{
    (e: 'cta'): void
}>()
</script>