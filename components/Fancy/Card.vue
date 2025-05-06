<!-- <template>
    <UCard :ui="{ base: 'overflow-hidden', header: { padding: '' }, footer: { base: 'grid grid-cols-2 divide-x', padding: '' } }">
        <template #header>
            <img src="/bnr-propertytax.jpg" alt="" class="object-cover object-center w-full h-48">
        </template>
        <div class="space-y-1 mb-4">
            <div class="flex items-center gap-2">
                <UIcon name="i-lucide-inbox" class="w-5 h-5 text-primary" /> <span class="font-light text-sm text-gray-500 dark:text-gray-400">Dolores</span>
            </div>
            <h3 class="font-semibold text-xl text-gray-800 dark:text-gray-100">
                SmartJuan24
            </h3>
        </div>
        
        <p class="font-light text-gray-500 dark:text-gray-400 leading-6">
            Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo dolorum soluta quos voluptas iusto perferendis ad error neque tempora mollitia?
        </p>
        <template #footer>
            <UButton label="Learn More" size="xl" variant="ghost" color="gray" :ui="{ base: 'justify-center h-14', rounded: 'rounded-none' }" />
            <UButton label="Learn More" size="xl" variant="ghost" color="gray" :ui="{ base: 'justify-center h-14', rounded: 'rounded-none' }" />
        </template>
    </UCard>
</template> -->

<template>
    <UCard
      :ui="{
        base: 'flex flex-col overflow-hidden',
        header: { padding: '' },
        body: { base: 'flex-1' },
        footer: { base: 'grid grid-flow-col divide-x dark:divide-gray-800', padding: '' }
      }"
    >
      <!-- Header Image -->
      <template v-if="image" #header>
        <img :src="image" :alt="title" class="object-cover object-center w-full h-48" />
      </template>
  
      <div class="space-y-1 mb-4" v-if="tag || title">
        <!-- Tag -->
        <div v-if="tag" class="flex items-center gap-2">
          <UIcon :name="icon || 'i-lucide-tag'" class="w-5 h-5 text-primary" />
          <span class="font-light text-sm text-gray-500 dark:text-gray-400">{{ tag }}</span>
        </div>
  
        <!-- Title -->
        <h3 v-if="title" class="font-semibold text-xl text-gray-800 dark:text-gray-100">
          {{ title }}
        </h3>
      </div>
  
      <!-- Description -->
      <p v-if="description" class="font-light text-gray-500 dark:text-gray-400 leading-6">
        {{ description }}
      </p>
  
      <!-- Footer Buttons -->
      <template v-if="buttons?.length" #footer>
        <UButton
          v-for="(btn, index) in buttons.slice(0, 2)"
          :key="index"
          :label="btn.label"
          :to="btn.to"
          size="xl"
          variant="ghost"
          color="gray"
          :ui="{ base: 'justify-center h-14', rounded: 'rounded-none' }"
        />
      </template>
    </UCard>
  </template>
  
  <script setup lang="ts">
  const props = defineProps<{
    image?: string
    icon?: string
    tag?: string
    title?: string
    description?: string
    buttons?: { label: string; to?: string }[]
  }>()
  </script>