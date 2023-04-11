<script>
export default {
    name: "PrimaryButton",

    data() {
        return {

        }
    },

    props: {
        text: "",

        type: "small",
    }
}
</script>

<template>
    <button :class="type">
        {{ text }}
    </button>
</template>

<style lang="scss" scoped>
button {
    background-color: #ef6f31;
    padding: 1rem 2rem;
    border: 0;
    border-radius: 5px;

    cursor: pointer;
    color: white;
    font-weight: bold;
    font-stretch: condensed;

    &:hover {
        background-color: #6ac5f1;
    }
}

button.small {
    padding: 0rem 1.5rem;
}
</style>
