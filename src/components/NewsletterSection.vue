<script>
export default {
    name: "NewsletterSection",

    data() {
        return {

        }
    },
}
</script>

<template>
    <section id="newsletter-section">
        <div id="newsletter-section-inner" class="container-small">
            <div id="newsletter-text">
                Newsletter to get in touch
            </div>

            <div id="newsletter-input">
                <input type="text" placeholder="Your e-mail">
                <button>&rightarrow;</button>
            </div>
        </div>
    </section>
</template>

<style lang="scss" scoped>
#newsletter-section {
    background-color: #244186;
    color: white;

    #newsletter-section-inner {
        padding: 3rem 1rem;

        display: flex;
        align-items: center;
        gap: 120px;

        #newsletter-text {
            width: 20%;
            font-size: 1.6rem;
            text-align: end;
        }

        #newsletter-input {
            width: 60%;
            height: 50px;
            border-bottom: 1px solid white;

            ::placeholder {
                color: white;
                font-size: 1.3rem;
            }

            input {
                background-color: transparent;
                width: 95%;
                height: 100%;
                border: 0;

                color: white;
                font-size: 1.3rem;

                &:focus-visible {
                    outline: 0;
                }
            }

            button {
                background-color: transparent;
                width: 5%;
                height: 100%;
                border: 0;

                color: white;
                font-size: 1.3rem;
                cursor: pointer;
            }
        }
    }
}
</style>