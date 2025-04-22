<template>
    <UForm ref="form" :schema="schema" :state="state" @submit="onSubmit" class="space-y-4">
        <UFormGroup label="Full Name" name="name" size="xl">
            <UInput v-model="state.name" />
        </UFormGroup>
        <UFormGroup label="Email Address" name="email" size="xl">
            <UInput v-model="state.email" />
        </UFormGroup>
        <UFormGroup label="Message" name="message" size="xl">
            <UTextarea v-model="state.message" resize :rows="8" />
        </UFormGroup>
        <div class="flex items-center gap-2">
            <UButton type="submit" label="Send Message" size="xl" color="black" :ui="{ rounded: 'rounded-full' }">
                <template #leading>
                    <UIcon name="i-lucide-send" class="w-5 h-5" />
                </template>
            </UButton>
            <UButton label="Clear" variant="outline" size="xl" :ui="{ rounded: 'rounded-full' }" @click="clearForm" />
        </div>
    </UForm>
</template>

<script setup lang="ts">
import { z } from 'zod'
import type { FormSubmitEvent } from '#ui/types'

const state = reactive({
    name: '',
    email: '',
    message: ''
})

const schema = z.object({
    name: z.string().min(10, 'Full Name must contain at least 10 character(s)'),
    email: z.string().email('Invalid email'),
    message: z.string().min(10, 'Message must contain at least 10 character(s)'),
})

type Schema = z.infer<typeof schema>

const form = ref()

async function onSubmit(event: FormSubmitEvent<Schema>) {
    // Do something with event.data
    console.log(event.data)
}

function clearForm() {
    // Reset the form fields
    state.name = ''
    state.email = ''
    state.message = ''

    // Reset validation (wait for next tick to ensure DOM updates)
    form.value?.clear?.()
}
</script>