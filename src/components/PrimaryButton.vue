<script>
export default {
    name: "PrimaryButton",

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
    background-color: #ef6f31;
    padding: 0 1.5rem;
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
</style>
