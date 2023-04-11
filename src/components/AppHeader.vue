<script>
import PrimaryButton from './PrimaryButton.vue';

export default {
    name: "AppHeader",

    data() {
        return {};
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

        <nav>
            navbar
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
}
</style>
