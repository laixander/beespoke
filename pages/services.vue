<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in services"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="grid grid-cols-1 lg:grid-cols-3 gap-y-10 gap-x-20">
                <Feature 
                    v-for="(feature, index) in features" 
                    :key="index" 
                    v-bind="feature"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlight />
    </AppSection>
</template>

<script setup lang="ts">
const services = [
    {
        title: 'Our Services',
        highlight: 'Our',
        paragraphs: [
            'At **Beespoke Solutions Inc.**, we offer a full suite of IT services designed to accelerate your digital transformation. From strategy to execution, our solutions are built to streamline operations, strengthen security, and drive sustainable business growth.'
        ]
    },
]
const features = [
    {
        icon: 'i-lucide-iteration-ccw',
        title: 'Technology Consulting',
        description: 'We provide strategic IT consulting to help businesses modernize infrastructure, manage risks, and drive innovation. Our experts guide you in building a scalable, secure, and future-ready tech environment.'
    },
    {
        icon: 'i-lucide-git-compare-arrows',
        title: 'Application Development',
        description: 'We design and develop custom applications that streamline operations, enhance user experiences, and support your business goals across digital platforms.'
    },
    {
        icon: 'i-lucide-users',
        title: 'QA And Testing',
        description: 'Our QA team ensures your software meets high standards of quality and performance—minimizing bugs, reducing risk, and securing system stability.'
    },
    {
        icon: 'i-lucide-iteration-ccw',
        title: 'Mobile Application Development',
        description: 'We build responsive, user-focused mobile apps that increase customer engagement, extend your brand reach, and support on-the-go access.'
    },
    {
        icon: 'i-lucide-git-compare-arrows',
        title: 'DevSecOps',
        description: 'We integrate development, operations, and security into one agile workflow—enabling faster releases without compromising protection.'
    },
    {
        icon: 'i-lucide-users',
        title: 'System Integration',
        description: 'We connect your systems, data, and applications to improve process efficiency, enable seamless communication, and enhance overall business performance.'
    }
]
</script>