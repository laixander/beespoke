<template>
    <AppHero />
    <AppSection isEven>
        <UContainer class="py-4 lg:py-20 space-y-16 lg:space-y-20">
            <FancyHeading title="Welcome to Beespoke Solutions Inc." highlight="Beespoke" align="center" />
            <div class="grid grid-cols-1 lg:grid-cols-[320px_320px_320px] gap-8 lg:gap-24 justify-center">
                <Feature v-for="(badge, index) in badges" :key="index" v-bind="badge" align="center" />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-2 gap-12 py-4 lg:py-20">
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                v-for="(item, index) in about"
                :key="index"
                :title="item.title"
                :highlight="item.highlight"
                :paragraphs="item.paragraphs"
            />
        </UContainer>
    </AppSection>
    <AppSection isEven>
        <UContainer class="py-4 lg:py-20 space-y-16">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in approach"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
            <div class="grid lg:grid-cols-3 gap-y-10 gap-x-20">
                <Feature v-for="(feature, index) in features" :key="index" v-bind="feature" />
            </div>
        </UContainer>
    </AppSection>
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

const features = [
    {
        icon: 'i-lucide-iteration-ccw',
        title: 'Agile Methodology',
        description: 'We embrace the Agile framework to ensure continuous improvement and flexibility. By delivering in iterative cycles, **Beespoke** drives high-performing results at every stage of development, adapting swiftly to change while staying focused on client goals.'
    },
    {
        icon: 'i-lucide-git-compare-arrows',
        title: 'CI/CD Pipeline',
        description: 'At **Beespoke**, automation is key. Our Continuous Integration and Continuous Deployment practices ensure that code changes are consistently built, tested, and delivered with reliability. This streamlined process reduces errors and accelerates time to market.'
    },
    {
        icon: 'i-lucide-users',
        title: 'Collaborative Culture',
        description: 'True innovation is a team effort. **Beespoke** fosters a collaborative environment where ideas are shaped together—turning vision into reality through open communication and shared ownership of success.'
    }
]

const about = [
    {
        title: 'Who We Are',
        highlight: 'We',
        paragraphs: [
            'In today’s fast-paced digital landscape, the impact of technological evolution is more evident than ever. Embracing innovation and adapting to the new normal is not just a choice—it’s a necessity. At **Beespoke Solutions Inc.**, we are committed to keeping pace with progress and delivering forward-thinking solutions that meet the needs of an ever-evolving community.',
            'As a cloud technology company, we bring a fresh perspective to information infrastructure. We don’t just support transformation—we enable it. By developing smart strategies and practical approaches, we drive meaningful change across workflows and business processes through intelligent automation.',
            'Our mission is to bridge the present with the future—empowering organizations to thrive in today’s dynamic environment while paving the way for sustainable success.'
        ]
    },
]

const approach = [
    {
        title: 'Our Approach',
        highlight: 'Our',
        paragraphs: [
            'At **Beespoke Solutions Inc.**, we believe that innovation thrives on structure, speed, and synergy. Our approach is grounded in modern methodologies that empower us—and our partners—to deliver exceptional results.'
        ]
    },
]
</script>