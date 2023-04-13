<script>
export default {
    name: "SocialList",

    data() {
        return {
            socialList: [
                {
                    icon: "fa-twitter",
                    link: "https://twitter.com/",
                },
                {
                    icon: "fa-facebook-f",
                    link: "https://it-it.facebook.com/",
                },
                {
                    icon: "fa-instagram",
                    link: "https://www.instagram.com/",
                },
                {
                    icon: "fa-linkedin",
                    link: "https://it.linkedin.com/",
                },
            ],
        }
    },
}
</script>

<template>
    <ul id="social-links">
        <li v-for="social in socialList" class="social-link">
            <a :href="social.link" target="_blank">
                <i class="fa-brands" :class="social.icon"></i>
            </a>
        </li>
    </ul>
</template>

<style lang="scss" scoped>
#social-links {
    display: flex;
    gap: 20px;

    i {
        color: #696969;
    }
}
</style>