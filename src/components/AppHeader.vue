<script>
import PrimaryButton from './PrimaryButton.vue';

export default {
    name: "AppHeader",

    data() {
        return {
            dropdownMenu: [
                {
                    title: "Home",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
                {
                    title: "Pages",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
                {
                    title: "Courses",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
                {
                    title: "Features",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
                {
                    title: "Blog",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
                {
                    title: "Shop",
                    links: [
                        "Link1",
                        "Link2",
                        "Link3",
                    ],
                    isActive: false,
                },
            ],

            socialList: [
                "fa-twitter",
                "fa-facebook-f",
                "fa-instagram",
                "fa-linkedin",
            ],
        };
    },

    components: {
        PrimaryButton,
    }
}
</script>

<template>
    <header>
        <div id="adv-bar">
            <p>
                <span id="adv-message">Starts TOMORROW! Our Biggest event of the years...</span>
                <i class="fa-regular fa-clock"></i>
                <span id="adv-time-left">00 : 00 : 00 : 00</span>
            </p>
            <PrimaryButton id="adv-button" :text="'Get ticket'"></PrimaryButton>
        </div>

        <nav class="container">
            <a id="navbar-logo" href="index.html">
                <img src="/images/dark-logo.png" alt="Logo MaxCoach">
            </a>

            <ul id="navbar-dropdown-menu">
                <li class="navbar-dropdown-item" v-for="dropdownItem in dropdownMenu"
                    @click="dropdownItem.isActive = !dropdownItem.isActive">
                    <div class="dropdown-item-title">
                        <p>{{ dropdownItem.title }}</p>
                        <i class="fa-solid fa-chevron-down"></i>
                    </div>
                    <ul v-show="dropdownItem.isActive" class="navbar-dropdown-item-links">
                        <li v-for="dropdownItemLink in dropdownItem.links">{{ dropdownItemLink }}</li>
                    </ul>
                </li>
            </ul>

            <ul id="social-links">
                <li v-for="social in socialList" class="social-link">
                    <a href="">
                        <i class="fa-brands" :class="social"></i>
                    </a>
                </li>
            </ul>
        </nav>

        <div id="jumbo">
            jumbo
        </div>
    </header>
</template>

<style lang="scss" scoped>
header {
    #adv-bar {
        background-color: #f5f5f5;
        padding: .5rem;

        display: flex;
        justify-content: center;
        gap: 50px;

        color: #333333;

        #adv-message {
            margin-right: 1rem;
            opacity: 70%;
        }

        i {
            margin-right: .5rem;
        }

        #adv-time-left {
            font-weight: bold;
        }
    }

    nav {
        padding: 2rem 0;

        display: flex;
        justify-content: space-between;
        align-items: center;

        #navbar-logo {
            height: 30px;

            img {
                height: 100%;
                width: auto;
            }
        }

        #navbar-dropdown-menu {
            display: flex;
            gap: 40px;

            .navbar-dropdown-item {
                position: relative;
                cursor: pointer;

                &:hover {
                    .dropdown-item-title {
                        p {
                            text-decoration: underline;
                        }
                    }
                }

                .dropdown-item-title {
                    display: flex;
                    align-items: center;
                    gap: .5rem;

                    i {
                        font-size: .5rem;
                    }
                }

                .navbar-dropdown-item-links {
                    border: 1px dotted black;
                    padding: 1rem .5rem;

                    display: flex;
                    flex-flow: column nowrap;
                    gap: 1rem;

                    position: absolute;
                }
            }
        }

        #social-links {
            display: flex;
            gap: 20px;

            i {
                color: #696969;
            }
        }
    }
}
</style>
