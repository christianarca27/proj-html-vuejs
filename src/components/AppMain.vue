<script>
import SecondaryButton from './SecondaryButton.vue';

export default {
    name: "AppMain",

    data() {
        return {
            services: [
                {
                    image: "artist-box-image-01.png",
                    name: "Online Courses",
                    description: "Online art coaching now offers you a very powerfull way to redesign your artist mind.",
                },
                {
                    image: "artist-box-image-02.png",
                    name: "One to One",
                    description: "Getting the necessary clarity about the current state to help you improve your ability.",
                },
                {
                    image: "artist-box-image-03.png",
                    name: "Antywhere",
                    description: "Access to valuable and portable program which allow you to setup and live anywhere you want.",
                },
                {
                    image: "artist-box-image-04.png",
                    name: "On Time",
                    description: "Punctuality is our top priority because it's an essential criteria to assess a program quality.",
                },
            ],
        }
    },

    components: {
        SecondaryButton,
    },
}
</script>

<template>
    <main>
        <section id="section-services">
            <div class="container">
                <h2>Artist Coaching</h2>

                <strong>I understand what it takes to create.<br> I can help you with</strong>

                <ul id="services-list">
                    <li v-for="service in services">
                        <img :src="'/images/' + service.image" alt="Sevice logo">
                        <h3>{{ service.name }}</h3>
                        <p>{{ service.description }}</p>
                    </li>
                </ul>

                <div id="goal">
                    <div id="goal-left">
                        <img src="/images/artist-quote-icon.png" alt="">
                        <strong>I coach and mentor visual artists, like you, to Create Like You Mean It</strong>
                        <span id="sign">Martin Garrix</span>
                    </div>
                    <div id="goal-right">
                        <p>As a coach and mentor, my ultimate goal is to motivate visual artists toward inspirated action. I
                            help you get you back on track to being the productive, creative, meaningful and authentic
                            artist
                            you truly want to be. I support artist in crafting and living a creative life as well as feeling
                            good about themselves and their art.</p>
                        <p>As an artist and an educator for nearly 30 years, I understand what it takes to create.</p>
                        <SecondaryButton :text="'Get started today'"></SecondaryButton>
                    </div>
                </div>
            </div>
        </section>

        <section>
        </section>
    </main>
</template>

<style lang="scss" scoped>
#section-services {
    padding: 50px 0;

    background-image: url("/images/maxcoach-shape-14.png");
    background-size: contain;
    background-position: top;
    background-repeat: no-repeat;

    .container {
        display: flex;
        flex-flow: column;
        align-items: center;

        h2 {
            font-size: 2rem;
        }

        strong {
            margin-bottom: 3rem;
            text-align: center;
            font-size: 1.7rem;
        }

        #services-list {
            display: flex;
            gap: 2rem;

            li {
                img {
                    height: 100px;
                    width: auto;
                }
            }

            li:nth-child(even) {
                position: relative;
                top: 30px;
            }
        }

        #goal {
            padding: 150px 0;

            display: flex;
            justify-content: center;
            gap: 100px;

            #goal-left {
                width: 25%;

                display: flex;
                flex-flow: column nowrap;
                align-items: center;
                gap: 1rem;

                text-align: center;

                strong {
                    font-size: 2.2rem;
                }

                #sign {
                    font-family: 'Caveat', cursive;
                    color: #6ac5f1;
                    font-size: 2rem;
                }
            }

            #goal-right {
                width: 35%;
                padding-top: calc(32px + 1rem);

                display: flex;
                flex-flow: column nowrap;
                align-items: start;
                gap: 2rem;
            }
        }
    }
}
</style>
