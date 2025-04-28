<template>
    <div
      v-if="icon"
      :class="unstyled || iconStyle
        ? iconStyle
        : [
            'inline-block',
            !unstyled && 'p-3 lg:p-4 bg-gradient-to-t from-primary-600 to-primary-400 rounded-full',
            iconStyle
          ]"
    >
      <UIcon
        :name="icon"
        :class="[
          'flex',
          iconSize || 'w-4 h-4 lg:w-6 lg:h-6',
          iconColor
            ? iconColor
            : iconStyle
              ? 'text-black'
              : unstyled
                ? 'text-primary-500'
                : 'text-white'
        ]"
      />
    </div>
  
    <UAvatar
      v-else-if="img"
      :src="img"
      :alt="imgAlt"
      :size="imgSize || '2xl'"
    />
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