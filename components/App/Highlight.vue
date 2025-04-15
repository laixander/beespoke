<template>
    <UContainer class="py-4 lg:py-20 space-y-16 lg:space-y-20">
        <FancyHeading title="Beespoke’s Strategic Milestones" highlight="Strategic" align="center" />
        <div class="grid grid-cols-1 lg:grid-cols-[320px_320px_320px] gap-8 lg:gap-24 justify-center">
            <Feature v-for="(badge, index) in badges" :key="index" v-bind="badge" align="center" />
        </div>
    </UContainer>
</template>

<script setup lang="ts">
const badges = [
    {
        img: '/badge.svg',
        imgSize: '3xl',
        description: '**First Full IT Outsourcing Project of the Government** of the Philippines.'
    },
    {
        img: '/badge.svg',
        imgSize: '3xl',
        description: '**First Chatbot of the Banking Industry** in the Philippines.'
    },
    {
        img: '/badge.svg',
        imgSize: '3xl',
        description: '**First Managed Service Provider of Kaspersky Lab** in the Philippines.'
    }
]
</script>