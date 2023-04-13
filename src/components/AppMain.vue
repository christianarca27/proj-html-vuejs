<script>
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
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
#section-services {
    background-image: url("/images/maxcoach-shape-14.png");
    background-size: contain;
    background-position: top;
    background-repeat: no-repeat;

    .container {
        padding: 2rem 0;

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
    }
}
</style>
