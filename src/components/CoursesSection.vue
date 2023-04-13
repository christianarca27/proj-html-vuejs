<script>
import SecondaryButton from './SecondaryButton.vue';

export default {
    name: "CoursesSection",

    data() {
        return {
            courses: [
                {
                    image: "artist-course-08-480x480.jpg",
                    price: 18,
                    title: "The Acrylic Painting Academy",
                    lessonsNum: 4,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-07-480x480.jpg",
                    price: 21,
                    title: "Drawing and Shading: Complete Course",
                    lessonsNum: 14,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-06-480x480.jpg",
                    price: 19,
                    title: "The Color Theory for Digital Artist",
                    lessonsNum: 7,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-05-480x480.jpg",
                    price: 35,
                    title: "Ultimate Guide to Digital Sketching for Beginner",
                    lessonsNum: 14,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-04-480x480.jpg",
                    price: 19,
                    title: "Protrait Drawing The Smart Way",
                    lessonsNum: 2,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-03-480x480.jpg",
                    price: 19,
                    title: "Mastering Watercolor Painting from Beginner",
                    lessonsNum: 9,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-02-480x480.jpg",
                    price: 25,
                    title: "The Art & Science of Drawing",
                    lessonsNum: 4,
                    studentsNum: 50,
                },
                {
                    image: "artist-course-01-480x480.jpg",
                    price: 22,
                    title: "The Colored Pencil Drawing Course",
                    lessonsNum: 6,
                    studentsNum: 50,
                },
            ],
        };
    },

    components: {
        SecondaryButton,
    },
}
</script>

<template>
    <section id="courses-section">
        <h2>Artist coaching</h2>

        <strong class="subtitle">Latest Online Courses</strong>

        <ul id="card-container" class="container">
            <li v-for="course in courses" class="card">
                <div class="card-image">
                    <img :src="'/images/' + course.image" alt="">
                </div>

                <div class="card-description">
                    <div class="card-price">${{ course.price.toFixed(2) }}</div>
                    <div class="card-title">{{ course.title }}</div>
                    <div class="card-details">
                        <span>
                            <i class="fa-regular fa-file-lines"></i> {{ course.lessonsNum }} Lessons
                        </span>
                        <span>
                            <i class="fa-solid fa-users"></i> {{ course.studentsNum }} Students
                        </span>
                    </div>
                </div>
            </li>
        </ul>

        <SecondaryButton :text="'View all courses &RightArrow;'"></SecondaryButton>
    </section>
</template>

<style lang="scss" scoped>
#courses-section {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;

    #card-container {
        margin-bottom: 2rem;

        display: flex;
        flex-flow: row wrap;
        gap: 40px;

        .card {
            width: calc(100% / 4 - 40px / 4 * 3);
            cursor: pointer;

            .card-image {
                img {
                    width: 100%;
                    aspect-ratio: 1;
                    object-fit: cover;
                }
            }

            .card-description {
                background-color: white;
                width: 90%;
                padding: 1rem;

                display: flex;
                flex-flow: column nowrap;
                gap: 1rem;

                .card-price {
                    color: #ef6f31;
                    font-weight: bold;
                }

                .card-title {
                    font-size: 1.2rem;
                    font-weight: bold;
                }

                .card-details {
                    display: flex;
                    gap: 1rem;

                    font-size: .8rem;
                    opacity: .8;
                }
            }

            &:hover {
                .card-description {
                    border: 1px solid #ef6f31;
                    position: relative;
                    top: -40px;
                    left: 0;
                }
            }
        }
    }
}
</style>