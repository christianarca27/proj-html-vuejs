<script>
export default {
    name: "BlogSection",

    data() {
        return {
            postList: [
                {
                    image: "artist-blog-03-480x356.jpeg",
                    type: "Artist",
                    title: "Brush Strokes Energize Trees in Paintings",
                    date: "May 15, 2020",
                    views: 688,
                },
                {
                    image: "artist-blog-02-500x680.jpg",
                    type: "Artist",
                    title: "Connection Between Self-Protraits and Identity",
                    date: "May 15, 2020",
                    views: 397,
                },
                {
                    image: "artist-blog-01-480x356.jpg",
                    type: "Artist",
                    title: "Pocket-Sized Notebooks Hold Miniature Paintings",
                    date: "May 15, 2020",
                    views: 603,
                },
            ],
        }
    },
}
</script>

<template>
    <section id="blog-section">
        <h2>Articles and Tips</h2>

        <strong class="subtitle">Latest From The Blog</strong>

        <ul id="card-container" class="container">
            <li v-for="post in postList" class="card">
                <div class="card-image">
                    <img :src="'/images/' + post.image" alt="Blog post image">
                </div>

                <div class="card-description">
                    <div class="card-type">{{ post.type }}</div>
                    <div class="card-title">{{ post.title }}</div>
                    <div class="card-details">
                        <div class="card-date">
                            <i class="fa-regular fa-calendar"></i>
                            {{ post.date }}
                        </div>
                        <div class="card-views">
                            <i class="fa-regular fa-eye"></i>
                            {{ post.views }} views
                        </div>
                    </div>
                </div>
            </li>
        </ul>

        <p id="view-all-post">Get into details now? <a href="">View all post &rightarrow;</a></p>
    </section>
</template>

<style lang="scss" scoped>
#blog-section {
    padding: 3rem 0;
    background-color: #f5f7fa;

    #card-container {
        margin-bottom: 3rem;

        display: flex;
        justify-content: center;
        align-items: center;
        gap: 3rem;

        .card {

            &:nth-of-type(1),
            &:nth-of-type(3) {
                width: 270px;
                height: 400px;


                .card-image {
                    height: 200px;

                    img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }
                }

                .card-description {
                    border: 1px solid black;
                    padding: 1.5rem;

                    .card-type {
                        text-transform: uppercase;
                        opacity: .7;
                    }

                    .card-title {
                        margin-bottom: 1rem;
                        font-weight: bold;
                        font-size: 1.2rem;
                    }

                    .card-details {
                        display: flex;
                        justify-content: space-between;

                        opacity: .7;
                    }
                }
            }

            &:nth-of-type(2) {

                width: 500px;
                height: 700px;

                position: relative;

                &::before {
                    background-color: black;
                    width: 100%;
                    height: 100%;

                    position: absolute;

                    content: "";
                    opacity: .2;
                }

                .card-image {
                    width: 100%;
                    height: 100%;

                    img {
                        width: 100%;
                        height: 100%;
                        object-fit: cover;
                    }
                }

                .card-description {
                    width: 100%;
                    padding: 3rem 2rem;

                    color: rgb(255, 255, 255);

                    position: absolute;
                    bottom: 0;
                    z-index: 1;

                    .card-type {
                        text-transform: uppercase;
                    }

                    .card-title {
                        margin-bottom: 1rem;
                        font-weight: bold;
                        font-size: 1.8rem;
                    }

                    .card-details {
                        display: flex;
                        gap: 2rem;
                    }
                }
            }

            &:last-of-type {
                position: relative;
                top: -100px;
            }
        }
    }

    #view-all-post {
        text-align: center;

        a {
            font-weight: bold;
            color: #ef6f31;
            text-decoration: none;
        }
    }
}
</style>

