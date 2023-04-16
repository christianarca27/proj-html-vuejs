<script>
export default {
    name: "EventsSection",

    data() {
        return {
            events: [
                {
                    image: "artist-event-04-250x300.jpg",
                    date: "Nov 22, 2020",
                    title: "Storytelling Workshop",
                    location: "Texas, US",
                },
                {
                    image: "artist-event-03-250x300.jpg",
                    date: "Oct 10, 2020",
                    title: "Painting Art Contest 2020",
                    location: "New York, US",
                },
                {
                    image: "artist-event-02-250x300.jpg",
                    date: "Nov 23, 2020",
                    title: "International Art Fair 2020",
                    location: "Hamburg, Germany",
                },
                {
                    image: "artist-event-01-250x300.jpg",
                    date: "Dec 15, 2020",
                    title: "Street Performance: Call for Artist",
                    location: "Illinois, US",
                },
            ],
        }
    },
}
</script>

<template>
    <section id="events-section">
        <h2>Upcoming Events</h2>

        <strong class="subtitle">Let's Work Together</strong>

        <ul id="card-container" class="container-small">
            <li v-for="event in events" class="card">
                <div class="card-image">
                    <img :src="'/images/' + event.image" alt="">
                </div>

                <div class="card-description">
                    <div class="card-date">{{ event.date }}</div>
                    <div class="card-title">{{ event.title }}</div>
                    <div class="card-location">
                        <i class="fa-solid fa-location-dot"></i>
                        {{ event.location }}
                    </div>
                </div>
            </li>
        </ul>
    </section>
</template>

<style lang="scss" scoped>
#events-section {
    padding: 50px 0;

    #card-container {
        display: flex;
        flex-flow: row wrap;
        gap: 60px;

        .card {
            width: calc(100% / 2 - 60px / 2);

            display: flex;
            align-items: center;

            cursor: pointer;

            .card-image {
                img {
                    display: block;
                    width: 250px;
                    height: 300px;
                    object-fit: cover;
                }
            }

            .card-description {
                padding: 2rem;

                .card-date {
                    margin-bottom: .5rem;
                    opacity: .7;
                    text-transform: uppercase;
                }

                .card-title {
                    margin-bottom: 1rem;
                    font-weight: bold;
                }

                .card-location {
                    font-size: .8rem;
                    opacity: .7;
                }
            }

            &:nth-last-child(1) .card-image,
            &:nth-last-child(2) .card-image {
                order: 1;
            }
        }
    }
}
</style>

