<template>
    <UContainer class="py-10 lg:py-20 space-y-8 lg:space-y-20">
        <FancyHeading title="Beespoke’s Strategic Milestones" highlight="Strategic" align="center" />
        <div class="grid grid-cols-1 lg:grid-cols-[320px_320px_320px] gap-8 lg:gap-24 justify-center">
            <Feature 
                v-for="(feature, index) in items" 
                :key="index" 
                v-bind="feature" 
                align="center" 
                img="/badge.svg"
                imgSize="3xl"
            />
        </div>
    </UContainer>
</template>

<script setup lang="ts">
import { items } from '@/data/highlights'
</script>