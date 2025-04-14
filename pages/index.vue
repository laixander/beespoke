<template>
    <AppHero />
    <AppSection isEven>
        <UContainer class="py-4 lg:py-20 space-y-20">
            <h3 class="font-semibold text-4xl text-center text-gray-800 dark:text-gray-100">
                Welcome to
                <span
                    class="before:block before:absolute before:-inset-1 before:-skew-y-3 before:bg-primary-500 relative inline-block">
                    <span class="relative text-white">Beespoke</span>
                </span>
                Solutions Inc.
            </h3>
            <div
                class="grid grid-cols-1 lg:grid-cols-3 gap-12 has-[p]:leading-7 has-[p]:text-center has-[p]:font-light has-[p]:text-gray-500 has-[p]:dark:text-gray-400">
                <div class="space-y-4">
                    <UAvatar src="/badge.svg" alt="No. 1" size="3xl" />
                    <p>
                        <strong class="font-semibold text-gray-600 dark:text-gray-200">First Full IT Outsourcing Project of
                            the Government</strong> of the Philippines.
                    </p>
                </div>

                <div class="space-y-4">
                    <UAvatar src="/badge.svg" alt="No. 1" size="3xl" />
                    <p>
                        <strong class="font-semibold text-gray-600 dark:text-gray-200">First Chatbot of the Banking
                            Industry</strong> in the Philippines.
                    </p>
                </div>

                <div class="space-y-4">
                    <UAvatar src="/badge.svg" alt="No. 1" size="3xl" />
                    <p>
                        <strong class="font-semibold text-gray-600 dark:text-gray-200">First Managed Service Provider of
                            Kaspersky Lab</strong> in the Philippines.
                    </p>
                </div>
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-2 gap-12 py-4 lg:py-20">
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <article
                class="prose max-w-none has-[p]:font-light has-[p]:text-gray-500 has-[p]:dark:text-gray-400">
                <h3 class="font-semibold text-4xl text-gray-800 dark:text-gray-100 lg:mb-8">
                    Who
                    <span
                        class="before:block before:absolute before:-inset-1 before:-skew-y-3 before:bg-primary-500 relative inline-block">
                        <span class="relative text-white">We</span>
                    </span>
                    Are
                </h3>
                <p>
                    In today’s fast-paced digital landscape, the impact of technological evolution is more evident than
                    ever. Embracing innovation and adapting to the new normal is not just a choice—it’s a necessity. At
                    Beespoke Solutions Inc., we are committed to keeping pace with progress and delivering
                    forward-thinking solutions that meet the needs of an ever-evolving community.
                </p>
                <p>
                    As a cloud technology company, we bring a fresh perspective to information infrastructure. We don’t
                    just support transformation—we enable it. By developing smart strategies and practical approaches,
                    we drive meaningful change across workflows and business processes through intelligent automation.
                </p>
                <p>
                    Our mission is to bridge the present with the future—empowering organizations to thrive in today’s
                    dynamic environment while paving the way for sustainable success.
                </p>
            </article>
        </UContainer>
    </AppSection>
    <AppSection isEven>
        <UContainer class="py-4 lg:py-20 space-y-16">
            <article class="prose max-w-none">
                <h3 class="font-semibold text-4xl text-gray-800 dark:text-gray-100 lg:mb-8">
                    <span
                        class="before:block before:absolute before:-inset-1 before:-skew-y-3 before:bg-primary-500 relative inline-block">
                        <span class="relative text-white">Our</span>
                    </span>
                    Approach
                </h3>
                <p class="font-light text-gray-500 dark:text-gray-400 lg:max-w-3xl text-pretty">At <strong class="font-semibold text-gray-600 dark:text-gray-300">Beespoke Solutions Inc.</strong>, we believe that innovation thrives on structure, speed, and synergy. Our approach is grounded in modern methodologies that empower us—and our partners—to deliver exceptional results.</p>
            </article>
            <div class="grid lg:grid-cols-3 gap-y-10 gap-x-20">
                <Feature v-for="(feature, index) in features" :key="index" v-bind="feature" />
            </div>
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
const features = [
    {
        icon: 'i-lucide-iteration-ccw',
        title: 'Agile Methodology',
        description: 'We embrace the Agile framework to ensure continuous improvement and flexibility. By delivering in iterative cycles, Beespoke drives high-performing results at every stage of development, adapting swiftly to change while staying focused on client goals.'
    },
    {
        icon: 'i-lucide-git-compare-arrows',
        title: 'CI/CD Pipeline',
        description: 'At Beespoke, automation is key. Our Continuous Integration and Continuous Deployment practices ensure that code changes are consistently built, tested, and delivered with reliability. This streamlined process reduces errors and accelerates time to market.'
    },
    {
        icon: 'i-lucide-users',
        title: 'Collaborative Culture',
        description: 'True innovation is a team effort. Beespoke fosters a collaborative environment where ideas are shaped together—turning vision into reality through open communication and shared ownership of success.'
    }
]
</script>