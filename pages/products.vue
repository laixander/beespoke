<template>
    <AppSection>
        <UContainer class="py-4 lg:py-20">
            <div class="lg:max-w-3xl">
                <Article
                    v-for="(item, index) in products"
                    :key="index"
                    :title="item.title"
                    :highlight="item.highlight"
                    :paragraphs="item.paragraphs"
                />
            </div>
        </UContainer>
    </AppSection>
    <AppSection>
        <UContainer class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center py-4 lg:py-20">
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="SmartJuan"
                highlight="Juan"
                :paragraphs="[
                    'Going digital is one of the best options you will want to consider, the digital technology change how the business world evolve, from the hustle and bustle of the city to the comfort of your home, from overwhelming application forms to uncomplicated e-submissions of forms. Republic Act 11032 or ease of doing business and efficient government service delivery act of 2018 is mandated to lessen the processing time of application and to promote transparency in the government offices.'
                ]"
            />

            <Article
                title="Real Property Tax Online Payment"
                highlight="Online"
                :paragraphs="[
                    'We commit to provide reliable systems for any E-services to our clients’ leverage, a well organize and straightforward software that is user-friendly. Transparency and accessibility is the basis of the digital market, and when we say technology it simultaneously means simple and convenient. Availability for faster and better service delivery is an edge, real-time collection of fees, able to track application progress and easy assessments can save much of your time, furthermore it is perfect matched for on the go tax payers.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="Digital Campus"
                highlight="Campus"
                :paragraphs="[
                    'Today’s education is leaning towards technology, with the increasing number of enrollees it is explicit that man power in inadequate to manage a bulk of forms and documents thus the need for Digital Experience Portal arises. It is important to create a cohesive web portal for them to have a touch point access to any hub, content and application. Design your portal with us and give your students the best academic environment and most engaging experience.'
                ]"
            />

            <Article
                title="Digital Learning"
                highlight="Learning"
                :paragraphs="[
                    'The transitioned from traditional to contemporary is fast so in these new normal times every learning professional should be electronically ready, from connections to devices to systems all must be in consonance. Learning Management System is design smartly to pile up e-learning materials in one place for a simultaneously study, it is developed to reduce production cost and to be accessible, it is configured to be flexible and easily monitored. No more excuses, let us personalize your website to continue the effectivity of learning and commence a diversify education.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="Human Resource Information System"
                highlight="Information"
                :paragraphs="[
                    'It’s about time to splash out on HR platform, spreadsheets can be too overwhelming plus the overlooked tasks that are either missed or duplicated. It is time for an upgrade in your office, make tracking every information hassle free and filter every search engines for a more efficient operation. Smoothly run through end to end process from finding leads, storing demographics, compensation and benefits to onboarding and finally deployment with a system seamlessly, innovatively and integratedly made.'
                ]"
            />

            <Article
                title="Payroll System"
                highlight="System"
                :paragraphs="[
                    'Compensations are the bread and butter of every employee; staffs are the asset of the organization hence it is critical matter where even minor error should have no room. Eliminate the complex computing, generate accurate pay slips, calculate bonuses and deductions fast and dodge from the strenuous compliance using a single database with confidence and ease. This is your sign to build the system that is exigency in your field.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="Financial System"
                highlight="System"
                :paragraphs="[
                    'One of the essential of an organization is the finance thus the need to refine to keep up in the ascent of society. A methodical approach is essential in every triumph of a business; it encompasses a flawless and durable system. Agree to an exemplary financing process, trouble-free invoicing and billing collection, polished budget planning and ensures compliance with tax and accounting regulations. Make the growth of your reputable business on top your priority, connect with us.'
                ]"
            />

            <Article
                title="Community Management System"
                highlight="Management"
                :paragraphs="[
                    'One of the benefits of having a marketing channel is you are able to manage clients’ complaint immediately, address queries and feedbacks, make your clients’ feel engaged and turning a customer to a loyal consumer while building rapport. Eye catching print advertisement, creative video presentation and influencers as referrals can boost your company. Moreover, a collaborative brand with a wide network is an addition in every successful enterprise.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="Tourist Management System"
                highlight="Management"
                :paragraphs="[
                    'Tourism generates revenue and is a big contributor in the economic growth. Weekend getaway is what we all want for after a long tiring Friday hence a lot of backpackers and wanderlust will instantly took over sites to booked their dream destinations. In addition huge number of data will be input that’s why there is a need for well founded, dynamic and responsive system to control records and manage accurate information.'
                ]"
            />

            <Article
                title="Public Market Administration System"
                highlight="Administration"
                :paragraphs="[
                    'Almost half of the population is now turning to their devices for inquires and purchases, consequently the demand for assistance is continuous. Along with websites comes with a clever software that stimulates human-like conversation or simply called chatbot. This will put up a massive contribution to the success of an enterprise with its tremendous impact in operations using its core function namely, to deliver a faster transaction, a good customer satisfaction score and a quality leads.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>
            <Article
                title="Hospital Management System"
                highlight="Management"
                :paragraphs="[
                    'Integrated system is a suitable approach to a progressive institution. The automated hospital management system will aide your trouble in keeping track to medical records, inventory management, patients’ data information, appointment booking and a whole lot of administrative job. Content management system will bridge you collaboratively to the clients. Let us assist you to customize and develop innovative software that will be in charge of hospitals functionalities and will command hospital operations.'
                ]"
            />

            <Article
                title="Tax Preparation System"
                highlight="Preparation"
                :paragraphs="[
                    'Accuracy, economical and efficacious are the gains you will have when you opt to have professional tax software. It is design to satisfy your need; the agility of the system you can rely on, the additional support you extremely need and the convenience you desire. Focus on you business’ core function, goal and mission, minimize the errors and save your energy; let our experts aid you in filling, computing and preparing for compliance and other tax returns.'
                ]"
            />
            <div class="bg-gray-100 dark:bg-gray-800 rounded-xl min-h-80"></div>

        </UContainer>
    </AppSection>
    <AppSection>
        <AppHighlight />
    </AppSection>
</template>

<script setup lang="ts">
const products = [
    {
        title: 'Our Products',
        highlight: 'Our',
        paragraphs: [
            '**Beespoke Solutions Inc.** develops innovative, purpose-driven digital products tailored to support government, education, and enterprise operations. From eGovernment platforms to fully integrated management systems, our solutions are built to simplify processes, enhance service delivery, and empower communities through smart technology.'
        ]
    },
]
</script>