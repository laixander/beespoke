<!-- <template>
    <ClientOnly>
        <UButton :icon="isDark ? 'i-heroicons-moon-20-solid' : 'i-heroicons-sun-20-solid'" color="gray" variant="ghost"
            aria-label="Theme" @click="isDark = !isDark" />
        <template #fallback>
            <div class="w-8 h-8" />
        </template>
    </ClientOnly>
</template>

<script setup lang="ts">
const colorMode = useColorMode()
const isDark = computed({
    get() {
        return colorMode.value === 'dark'
    },
    set() {
        colorMode.preference = colorMode.value === 'dark' ? 'light' : 'dark'
    }
})
</script> -->

<template>
    <div class="flex items-center gap-4">
        <!-- Light/Dark mode switcher -->
        <UButton :icon="isDark ? 'i-ri-sun-fill' : 'i-ri-moon-fill'" variant="link" aria-label="Toggle Dark Mode"
            @click="toggleDark" />
        <!-- Color theme switcher -->
        <UButton icon="i-ri-paint-fill" variant="link" aria-label="Color Theme" @click="changeColorTheme" />
    </div>
</template>

<script setup lang="ts">
import colors from '#tailwind-config/theme/colors'

const appConfig = useAppConfig()
const colorMode = useColorMode()
const { createNotification } = useNotifications()

const isDark = computed(() => colorMode.value === 'dark')

const toggleDark = () => {
    colorMode.preference = isDark.value ? 'light' : 'dark'
    createNotification(
        'Application Theme Updated',
        `Theme was set to ${colorMode.preference}`,
        3000,
        isDark.value ? 'i-ri-sun-fill' : 'i-ri-moon-fill',
        appConfig.ui.primary
    )
}

const primaryColors = computed(() =>
    appConfig.ui.colors
        .filter((color) => color !== 'primary')
        .map((color) => ({
            value: color,
            text: color,
            hex: colors[color][isDark.value ? 400 : 500]
        }))
)

let curr = 0
const changeColorTheme = () => {
    const lastIndex = primaryColors.value.length - 1
    curr = (curr + 1) % (lastIndex + 1)

    appConfig.ui.primary = primaryColors.value[curr].value
    window.localStorage.setItem('nuxt-ui-primary', appConfig.ui.primary)

    createNotification(
        'Color Theme Updated',
        `Color theme was set to ${appConfig.ui.primary}`,
        3000,
        'i-ri-paint-fill',
        appConfig.ui.primary
    )
}
</script>