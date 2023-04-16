<script>
import BlogSection from './BlogSection.vue';
import CoursesSection from './CoursesSection.vue';
import EventsSection from './EventsSection.vue';
import ServicesSection from './ServicesSection.vue';

export default {
    name: "AppMain",
    data() {
        return {};
    },

    components: {
        ServicesSection,
        CoursesSection,
        BlogSection,
        EventsSection
    },
}
</script>

<template>
    <main>
        <ServicesSection></ServicesSection>

        <CoursesSection></CoursesSection>

        <BlogSection></BlogSection>

        <EventsSection></EventsSection>
    </main>
</template>

<style lang="scss" scoped></style>
