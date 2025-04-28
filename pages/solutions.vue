<template>
    <AppBanner>
        <UContainer class="py-10 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article v-for="(item, index) in banner" :key="index" :title="item.title" :highlight="item.highlight"
                    :paragraphs="item.paragraphs" />
            </div>
        </UContainer>
    </AppBanner>
    <AppSection>
        <!-- <UContainer class="grid grid-cols-1 lg:grid-cols-3 gap-10 py-4 lg:py-20">
            <FancyCard
                v-for="(product, index) in products"
                :key="index"
                v-bind="product"
                iconStyle="bg-white/60 dark:bg-white/10 rounded-full p-4"
            />
        </UContainer> -->

        <!-- Inline Component: Articles with Images with Alternate Position-->
        <UContainer class="grid gap-10 lg:gap-20 py-10 lg:py-20">
            <div v-for="(item, index) in items" :key="index" class="grid lg:grid-cols-2 gap-8 items-center">
                <!-- Image -->
                <div :class="index % 2 === 1 ? 'lg:order-2' : ''" class="bg-primary-200 dark:bg-primary-950 rounded-xl h-full shadow-md overflow-hidden">
                    <img :src="item.image" :alt="item.title" class="w-full" />
                </div>

                <!-- Article -->
                <div :class="index % 2 === 1 ? 'lg:order-1' : ''" class="space-y-8" >
                    <Article :title="item.title" :paragraphs="item.paragraphs" size="text-2xl" hasDivider />
                    <UButton label="Talk to our expert" color="white" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
                </div>
            </div>
        </UContainer>
        
    </AppSection>
    <AppSection>
        <UContainer class="text-center py-10 lg:py-20">
            <FancyHeading 
                title="Ready to transform your public services?"
                size="text-3xl"
            />
            <FancyDivider align="center" />
            <p class="prose mx-auto dark:text-gray-400 mb-8">
                Contact us today to learn how our digital solutions can help your organization deliver better services to your community.
            </p>
            <UButton label="Get Started" size="xl" :ui="{ rounded: 'rounded-full', padding: { xl: 'px-6' } }" />
        </UContainer>
    </AppSection>
</template>

<script setup lang="ts">
import { banner, products, items } from '@/data/solutions'

// const products = [
//     {
//         title: 'SmartJuan: eGovernment Service Platform',
//         description:
//             'A **unified digital gateway** designed to simplify public service delivery. SmartJuan empowers citizens with **fast**, **transparent**, and **accessible** government transactions — aligned with *Republic Act 11032* to promote efficiency and reduce processing times across agencies.',
//         icon: 'i-lucide-globe',
//         iconColor: 'text-blue-500',
//         headerBackground: 'bg-blue-100 dark:bg-blue-950',
//     },
//     {
//         title: 'Real Property Tax Payment System',
//         description:
//             'Say goodbye to long queues and paperwork. Our **real-time payment platform** streamlines assessments, tracking, and collections — giving taxpayers a **hassle-free** way to stay compliant from anywhere, anytime.',
//         icon: 'i-lucide-wallet',
//         iconColor: 'text-amber-500',
//         headerBackground: 'bg-amber-100 dark:bg-amber-950',
//     },
//     {
//         title: 'Digital Campus',
//         description:
//             'Transform your institution with a **centralized portal** built for modern education. Digital Campus connects students, faculty, and administrators through a **seamless digital hub** that supports **enrollment**, **learning tools**, and **student services**.',
//         icon: 'i-lucide-graduation-cap',
//         iconColor: 'text-indigo-500',
//         headerBackground: 'bg-indigo-100 dark:bg-indigo-950',
//     },
//     {
//         title: 'Digital Learning Platform',
//         description:
//             'Adapt to the evolving learning landscape with a **smart**, **flexible system** that centralizes e-learning materials, simplifies access, and supports **dynamic**, **monitored education**. Designed to make digital learning **efficient** and **scalable**.',
//         icon: 'i-lucide-laptop',
//         iconColor: 'text-cyan-500',
//         headerBackground: 'bg-cyan-100 dark:bg-cyan-950',
//     },
//     {
//         title: 'Human Resource Information System (HRIS)',
//         description:
//             'Modernize HR operations with a system that simplifies **employee management** — from recruitment to retirement. Store, track, and analyze employee data **securely** while improving overall workflow and efficiency.',
//         icon: 'i-lucide-users',
//         iconColor: 'text-fuchsia-500',
//         headerBackground: 'bg-fuchsia-100 dark:bg-fuchsia-950',
//     },
//     {
//         title: 'Payroll Automation System',
//         description:
//             'Ensure **timely** and **accurate compensation** with a payroll system that automates calculations, tax deductions, and compliance. Eliminate errors and deliver **peace of mind** to both HR and employees.',
//         icon: 'i-lucide-banknote',
//         iconColor: 'text-lime-500',
//         headerBackground: 'bg-lime-100 dark:bg-lime-950',
//     },
//     {
//         title: 'Financial Management System',
//         description:
//             'Manage your organization’s finances with confidence. Our solution streamlines **budgeting**, **invoicing**, **collections**, and **financial reporting** — ensuring **accuracy**, **transparency**, and full **regulatory compliance**.',
//         icon: 'i-lucide-pie-chart',
//         iconColor: 'text-orange-500',
//         headerBackground: 'bg-orange-100 dark:bg-orange-950',
//     },
//     {
//         title: 'Community Engagement Platform',
//         description:
//             'Foster strong community connections through **responsive client interactions**. From support inquiries to feedback management, this system keeps **communication clear** and **relationships thriving**.',
//         icon: 'i-lucide-message-square-dot',
//         iconColor: 'text-rose-500',
//         headerBackground: 'bg-rose-100 dark:bg-rose-950',
//     },
//     {
//         title: 'Tourism Management System',
//         description:
//             'Support tourism operations with a platform that handles **bookings**, **guest data**, and **site management** in real time. Ideal for LGUs and tourism offices looking to **scale services** and **enhance visitor experiences**.',
//         icon: 'i-lucide-map-pin',
//         iconColor: 'text-teal-500',
//         headerBackground: 'bg-teal-100 dark:bg-teal-950',
//     },
//     {
//         title: 'Public Market Management System',
//         description:
//             'Digitize and manage public market operations with a platform that supports **stall assignments**, **billing**, **inventory**, and **vendor data**. Built for **efficiency**, **transparency**, and better service delivery.',
//         icon: 'i-lucide-shopping-cart',
//         iconColor: 'text-purple-500',
//         headerBackground: 'bg-purple-100 dark:bg-purple-950',
//     },
//     {
//         title: 'Hospital Management System',
//         description:
//             'Streamline hospital operations with a centralized platform for **patient records**, **inventory**, and **appointments**. Designed for **efficiency**, **accuracy**, and **better healthcare delivery**.',
//         icon: 'i-lucide-heart-pulse',
//         iconColor: 'text-green-500',
//         headerBackground: 'bg-green-100 dark:bg-green-950',
//     },
//     {
//         title: 'Tax Preparation System',
//         description:
//             'Automate and simplify **tax computations**, **filings**, and **compliance**. Designed to **minimize errors** and reduce stress, this platform helps both businesses and agencies stay aligned with **tax regulations** efficiently.',
//         icon: 'i-lucide-file-text',
//         iconColor: 'text-yellow-500',
//         headerBackground: 'bg-yellow-100 dark:bg-yellow-950',
//     },
// ]
</script>