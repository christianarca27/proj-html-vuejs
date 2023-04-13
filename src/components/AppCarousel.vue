<script>
export default {
    name: "AppCarousel",

    data() {
        return {
            reviews: [
                {
                    title: "It's a choice of quality for people with special needs",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Soluta modi officiis quasi unde eaque ut eum, nam nobis ducimus quibusdam tenetur harum adipisci, optio omnis ab, asperiores eligendi ipsum iure.",
                    userImage: "artist-testimonial-avatar-01.jpg",
                    username: "Florence Themes",
                    userRole: "Multimedia Admin",
                },
                {
                    title: "High level of efficiency and scientific teaching methods",
                    text: "I am free to learn at my own pace, follow my own schedule and choose the subject I want to learn from the syllabus. Great study portal for people like me.",
                    userImage: "artist-testimonial-avatar-02.jpg",
                    username: "Mina Hollace",
                    userRole: "Freelancer",
                },
                {
                    title: "Professional team of specialist and passionate mentors at reach",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Soluta modi officiis quasi unde eaque ut eum, nam nobis ducimus quibusdam tenetur harum adipisci, optio omnis ab, asperiores eligendi ipsum iure.",
                    userImage: "artist-testimonial-avatar-03.jpg",
                    username: "Madley Pondor",
                    userRole: "IT Specialist",
                },
                {
                    title: "Test review",
                    text: "Lorem ipsum dolor sit amet, consectetur adipisicing elit. Soluta modi officiis quasi unde eaque ut eum, nam nobis ducimus quibusdam tenetur harum adipisci, optio omnis ab, asperiores eligendi ipsum iure.",
                    userImage: "artist-testimonial-avatar-04.jpg",
                    username: "Ricky Brown",
                    userRole: "Designer",
                },
            ],

            activeIndex: 0,
        }
    },

    computed: {
        previousIndex() {
            if (this.activeIndex > 0) {
                return this.activeIndex - 1;
            }
            else {
                return this.activeIndex + this.reviews.length - 1;
            }
        },

        nextIndex() {
            if (this.activeIndex < this.reviews.length - 1) {
                return this.activeIndex + 1;
            }
            else {
                return (this.activeIndex + 1) % this.reviews.length;
            }
        }
    },
}
</script>

<template>
    <div id="reviews-list-wrapper">
        <ul id="reviews-list">
            <li class="review" @click="activeIndex = previousIndex">
                <div class="review-title">
                    {{ reviews[previousIndex].title }}
                </div>

                <div class="review-text">
                    {{ reviews[previousIndex].text }}
                </div>

                <div class="review-user">
                    <div class="review-user-icon">
                        <img :src="'/images/' + reviews[previousIndex].userImage" alt="User image">
                    </div>

                    <div class="review-user-details">
                        <strong class="review-username">{{ reviews[previousIndex].username }}</strong>
                        <div class="review-user-role">/ {{ reviews[previousIndex].userRole }}</div>
                    </div>
                </div>
            </li>

            <li class="review active">
                <div class="review-title">
                    {{ reviews[activeIndex].title }}
                </div>

                <div class="review-text">
                    {{ reviews[activeIndex].text }}
                </div>

                <div class="review-user">
                    <div class="review-user-icon">
                        <img :src="'/images/' + reviews[activeIndex].userImage" alt="User image">
                    </div>

                    <div class="review-user-details">
                        <strong class="review-username">{{ reviews[activeIndex].username }}</strong>
                        <div class="review-user-role">/ {{ reviews[activeIndex].userRole }}</div>
                    </div>
                </div>
            </li>

            <li class="review" @click="activeIndex = nextIndex">
                <div class="review-title">
                    {{ reviews[nextIndex].title }}
                </div>

                <div class="review-text">
                    {{ reviews[nextIndex].text }}
                </div>

                <div class="review-user">
                    <div class="review-user-icon">
                        <img :src="'/images/' + reviews[nextIndex].userImage" alt="User image">
                    </div>

                    <div class="review-user-details">
                        <strong class="review-username">{{ reviews[nextIndex].username }}</strong>
                        <div class="review-user-role">/ {{ reviews[nextIndex].userRole }}</div>
                    </div>
                </div>
            </li>
        </ul>

        <div id="rotate-commands">
            <i v-for="(review, index) in reviews" class="fa-solid fa-circle" :class="index == activeIndex ? 'active' : ''"
                @click="activeIndex = index"></i>
        </div>
    </div>
</template>

<style lang="scss" scoped>
#reviews-list-wrapper {
    display: flex;
    flex-flow: column nowrap;
    align-items: center;
    padding: 0 50px;

    #reviews-list {
        display: flex;
        margin-bottom: 2rem;

        flex-flow: row nowrap;
        gap: 50px;
        overflow: hidden;

        .review {
            background-color: white;
            width: calc(100% / 3 - 50px / 3 * 2);
            padding: 2rem;
            flex-shrink: 0;
            opacity: .5;
            cursor: pointer;

            &>* {
                margin-bottom: 1rem;
            }

            &.active {
                opacity: 1;
            }

            .review-title {
                font-weight: bold;
                font-size: 1.2rem;
            }

            .review-text {}

            .review-user {
                display: flex;
                align-items: center;
                gap: 2rem;

                .review-user-icon {
                    img {
                        width: 80px;
                        height: 80px;
                        border-radius: 40px;
                    }
                }
            }
        }
    }

    #rotate-commands {
        display: flex;
        align-items: center;
        gap: 1rem;

        i {
            font-size: .3rem;
            opacity: .5;
            cursor: pointer;

            &:hover {
                font-size: .5rem;
            }

            &.active {
                font-size: .5rem;
                opacity: 1;
            }
        }
    }
}
</style>