<script>
import CoursesSection from './CoursesSection.vue';
import ServicesSection from './ServicesSection.vue';

export default {
    name: "AppMain",
    data() {
        return {};
    },

    components: {
        ServicesSection,
        CoursesSection,
    },
}
</script>

<template>
    <main>
        <ServicesSection></ServicesSection>

        <CoursesSection></CoursesSection>
    </main>
</template>

<style lang="scss" scoped></style>
