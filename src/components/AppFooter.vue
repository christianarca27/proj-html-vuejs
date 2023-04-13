<script>
import PrimaryButton from './PrimaryButton.vue';
import SocialList from './SocialList.vue';

export default {
    name: "AppFooter",

    data() {
        return {
            info: {
                address: "382 NE 191st St # 87394 Miami, FL 33179-3899",
                phoneNumber: "+1(305)547-9909",
                openingTime: "9am - 5pm EST, Monday - Friday",
                email: "support@maxcoach.com",
            },

            footerLinks: [
                {
                    title: "Explore",
                    links: [
                        {
                            linkName: "Start here",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Success story",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Blog",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Courses",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Contact us",
                            linkAddress: "#",
                        },
                    ],
                },
                {
                    title: "Information",
                    links: [
                        {
                            linkName: "Membership",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Purchase guide",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Privacy policy",
                            linkAddress: "#",
                        },
                        {
                            linkName: "Terms of services",
                            linkAddress: "#",
                        },
                    ],
                },
            ],

            instagramPreview: {
                username: "@maxcoach",
                photos: [
                    "120084500_197897808368764_8114555493043279565_n.jpg",
                    "120012142_177596140500760_8623485824101406058_n.jpg",
                    "120099363_364334431619755_7198812647386067017_n.jpg",
                ]
            }
        };
    },
    components: {
        SocialList,
        PrimaryButton
    }
}
</script>

<template>
    <footer class="container">
        <ul id="footer-top">
            <li id="address">
                <strong>Address</strong>
                <p>{{ info.address }}</p>
                <p>{{ info.phoneNumber }} ({{ info.openingTime }})</p>
                <p>{{ info.email }}</p>
                <SocialList></SocialList>
            </li>

            <li id="footer-links" v-for="linkList in footerLinks">
                <ul>
                    <li>
                        <strong>{{ linkList.title }}</strong>
                    </li>
                    <li v-for="link in linkList.links">
                        <a :href="link.linkAddress">{{ link.linkName }}</a>
                    </li>
                </ul>
            </li>

            <li id="instagramPreview">
                <strong>Instagram <span class="orange">{{ instagramPreview.username }}</span></strong>
                <ul>
                    <li v-for="photo in instagramPreview.photos">
                        <img :src="'/images/' + photo" alt="">
                    </li>
                </ul>
            </li>
        </ul>
        <div id="footer-bottom">
            <a href="#">
                <PrimaryButton id="btn-return" :type="'circle'" :text="'&UpArrow;'"></PrimaryButton>
            </a>
            <span id="credits">&copy; 2020 Maxcoach. All Rights Reserved</span>
        </div>
    </footer>
</template>

<style lang="scss" scoped>
strong {
    display: block;
    margin-bottom: 1rem;
    font-size: 1rem;
}

.orange {
    color: #ef6f31;
}

footer {
    padding: 5rem 0 2rem 0;
    font-size: .8rem;

    #footer-top {
        margin-bottom: 3rem;

        display: flex;
        justify-content: space-between;

        #address {
            p {
                margin-bottom: .8rem;
            }
        }

        #footer-links {
            li {
                margin-bottom: .8rem;

                a {
                    color: black;
                    text-decoration: none;

                    &:hover {
                        text-decoration: underline;
                    }
                }
            }
        }

        #instagramPreview {
            ul {
                display: flex;
                gap: 1rem;

                li {
                    img {
                        width: 130px;
                        height: 130px;
                        object-fit: contain;

                        cursor: pointer;
                    }
                }
            }
        }
    }

    #footer-bottom {
        text-align: center;

        #btn-return {
            position: fixed;
            bottom: 20px;
            right: 10px;
        }
    }
}
</style>
