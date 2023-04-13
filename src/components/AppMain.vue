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
            <h2>Artist Coaching</h2>

            <strong>I understand what it takes to create.<br> I can help you with</strong>

            <div class="background-white">
                <div id="services-list" class="container-small">
                    <ul>
                        <li v-for="service in services">
                            <img :src="'/images/' + service.image" alt="Sevice logo">
                            <h3>{{ service.name }}</h3>
                            <p>{{ service.description }}</p>
                        </li>
                    </ul>
                </div>

                <div id="goal" class="container-small">
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

                <div id="video-post" class="container-small">
                    <img id="video-post-shape-1" src="/images/maxcoach-shape-05-150x150.png" alt="">
                    <img id="video-post-shape-2" src="/images/maxcoach-shape-12-150x150.png" alt="">
                    <img id="btn-play-youtube" src="/images/icon-youtube-play.png" alt="Youtube play button">
                    <img id="video-post-cover" src="/images/artist-video-poster.jpg" alt="Poster video Youtube">
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


    h2 {
        text-align: center;
        font-size: 2rem;
    }

    strong {
        display: block;
        margin-bottom: 3rem;
        text-align: center;
        font-size: 1.7rem;
    }

    #services-list {
        ul {
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
    }

    #goal {
        padding: 150px 0;

        display: flex;
        justify-content: space-between;

        #goal-left {
            width: 40%;

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
            width: 50%;
            padding-top: calc(32px + 1rem);

            display: flex;
            flex-flow: column nowrap;
            align-items: start;
            gap: 2rem;
        }
    }

    #video-post {
        width: 50%;

        display: flex;
        justify-content: center;

        position: relative;

        #video-post-shape-1 {
            position: absolute;
            top: -30px;
            left: -30px;
        }

        #video-post-shape-2 {
            position: absolute;
            bottom: -10px;
            right: -100px;
        }

        #btn-play-youtube {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            z-index: 2;
            cursor: pointer;
        }

        #video-post-cover {
            width: 100%;
            z-index: 1;
        }
    }
}
</style>
