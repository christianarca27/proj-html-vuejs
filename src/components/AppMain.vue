<script>
import BlogSection from './BlogSection.vue';
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
        BlogSection
    },
}
</script>

<template>
    <main>
        <ServicesSection></ServicesSection>

        <CoursesSection></CoursesSection>

        <BlogSection></BlogSection>
    </main>
</template>

<style lang="scss" scoped></style>
