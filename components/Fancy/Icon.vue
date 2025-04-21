<template>
    <div v-if="icon" :class="[
        'inline-block',
        !unstyled && 'p-4 bg-gradient-to-t from-primary-600 to-primary-400 rounded-full',
        iconStyle // apply custom wrapper styles here
    ]">
        <UIcon
            :name="icon"
            :class="[
                'flex',
                iconSize || 'w-6 h-6',
                unstyled
                ? (iconColor || 'text-primary-500')
                : (iconColor || 'text-white')
            ]"
        />
    </div>

    <UAvatar v-else-if="img" :src="img" :alt="imgAlt" :size="imgSize || '2xl'" />
</template>

<script setup lang="ts">
const props = defineProps<{
    icon?: string //use icon and set name
    unstyled?: boolean //remove icon wrapper style
    iconColor?: string //set icon class color
    iconStyle?: string //set icon wrapper style
    iconSize?: string //set icon class size
    img?: string //use image and set src
    imgAlt?: string //set image alt tag
    imgSize?: any //set image size
}>()
</script>