<template>
    <UCard :ui="{
        base: 'overflow-hidden',
        header: { base: `flex items-center gap-4 ${headerAlign}`, background: headerBackground, padding: 'px-4 py-2 sm:px-6 sm:py-4' },
        footer: { base: 'border-none' }
    }">
        <template #header>
            <FancyIcon v-if="icon || img" :icon="icon" :img="img" :imgAlt="imgAlt" :iconStyle="iconStyle"
                :iconColor="iconColor" :iconSize="iconSize" />
            <h3 class="font-bold leading-tight lg:leading-snug lg:text-lg text-gray-800 dark:text-gray-100">
                {{ title }}
            </h3>
        </template>
        <slot>
            <Markdown :text="description" :class="descriptionAlignClass" />
        </slot>
        <template #footer v-if="buttonLabel">
            <UButton :label="buttonLabel" size="xl" block />
        </template>
    </UCard>
</template>

<script setup lang="ts">
const props = defineProps<{
    title: string
    description: string
    icon?: string
    iconColor?: string
    iconStyle?: string
    iconSize?: string
    img?: string
    imgAlt?: string
    buttonLabel?: string
    align?: 'left' | 'center' | 'right'
    headerBackground?: string
}>()

const headerAlign = computed(() => {
    return props.align === 'center'
        ? 'justify-center text-center'
        : props.align === 'right'
            ? 'justify-end text-right'
            : 'justify-start text-left'
})

const descriptionAlignClass = computed(() => {
    return props.align === 'center'
        ? 'text-center'
        : props.align === 'right'
            ? 'text-right'
            : 'text-left'
})
</script>