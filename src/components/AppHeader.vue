<script>
import PrimaryButton from './PrimaryButton.vue';
import SocialList from './SocialList.vue'

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
        };
    },

    components: {
        PrimaryButton,
        SocialList,
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
            <PrimaryButton id="adv-button" :type="'small'" :text="'Get ticket'"></PrimaryButton>
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

            <SocialList></SocialList>
        </nav>

        <div id="jumbo">
            <img id="jumbo-shape-1" src="/images/artist-shape-02-768x415.png" alt="">
            <img id="jumbo-shape-2" src="/images/artist-shape-03.png" alt="">
            <img id="jumbo-shape-3" src="/images/artist-hero-image-03-204x300.png" alt="">
            <img id="jumbo-shape-4" src="/images/artist-hero-image-02-232x300.jpg" alt="">
            <img id="jumbo-shape-5" src="/images/artist-hero-image-01.jpg" alt="">
            <div id="jumbo-inner">
                <h1>Hello, Im Matin</h1>
                <strong>Artist Coaching And Mentoring<br> Might Be for You.</strong>
                <PrimaryButton :text="'Get started today'"></PrimaryButton>
            </div>
            <img id="jumbo-shape-6" src="/images/artist-shape-01-600x577.png" alt="">
            <img id="jumbo-shape-7" src="/images/artist-shape-04-127x300.png" alt="">
            <img id="jumbo-shape-8" src="/images/artist-shape-05-300x198.png" alt="">
            <img id="jumbo-shape-9" src="/images/artist-hero-image-04-235x300.jpg" alt="">
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
    }

    #jumbo {
        height: 600px;

        display: flex;
        justify-content: center;
        align-items: center;

        position: relative;
        overflow: hidden;

        img {
            position: absolute;
        }

        #jumbo-shape-1 {
            top: 0;
            left: 0;
        }

        #jumbo-shape-2 {
            top: 50%;
            left: 2%;
            transform: translateY(-50%);
        }

        #jumbo-shape-3 {
            top: 40%;
            left: 23%;
        }

        #jumbo-shape-4 {
            top: 10%;
            left: 18%;
        }

        #jumbo-shape-5 {
            top: 49%;
            left: 8%;
        }

        #jumbo-inner {
            display: flex;
            flex-flow: column nowrap;
            align-items: center;
            gap: 30px;

            z-index: 1;
            text-align: center;

            h1 {
                font-size: 3rem;
            }

            strong {
                font-size: 1.5rem;
            }
        }

        #jumbo-shape-6 {
            top: 0;
            right: 10%;
        }

        #jumbo-shape-7 {
            top: 5%;
            right: 10%;
        }

        #jumbo-shape-8 {
            top: 55%;
            right: 5%;
        }

        #jumbo-shape-9 {
            top: 30%;
            right: 15%;
        }
    }
}
</style>
