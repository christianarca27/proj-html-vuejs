<script>
export default {
    name: "SecondaryButton",

    data() {
        return {

        }
    },

    props: {
        text: "",
    }
}
</script>

<template>
    <button>
        {{ text }}
    </button>
</template>

<style lang="scss" scoped>
button {
    background-color: #ef6f3128;
    padding: 1rem 2rem;
    border: 0;
    border-radius: 5px;

    cursor: pointer;
    color: #ef6f31;
    font-weight: bold;
    font-stretch: condensed;

    &:hover {
        background-color: #6ac4f128;
    }
}

button.small {
    padding: 0rem 1.5rem;
}

button.circle {
    padding: 0;
    width: 50px;
    aspect-ratio: 1;
    border-radius: 25px;

    display: flex;
    justify-content: center;
    align-items: center;

    font-size: 1.2rem;
}
</style>
