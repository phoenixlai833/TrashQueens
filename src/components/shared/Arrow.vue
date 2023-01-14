<template>
    <button class="arrow" :class="variant">
        <Iconify :iconName="arrowName" :iconColor="arrowColor" :iconHeight="arrowHeight" />
    </button>
</template>

<script>
import Iconify from './Iconify.vue';

export default {
    name: "Arrow",
    methods: {},
    computed: {},
    props: {
        variant: {
            type: String,
            required: false
        },
        arrowName: {
            type: String,
            required: true
        },
        arrowColor: {
            type: String,
            required: true
        },
        arrowHeight: {
            type: Number,
            required: true
        }
    },
    data() {
        return {};
    },
    components: { Iconify }
};
</script>

<style scoped>

.arrow {
    display: flex;
    align-items: center;
    justify-content: center;
    border: none;
    background-color: transparent;
    cursor: pointer;
    outline: none;
    opacity: 0.3;
    transition: all 0.2s ease-in-out;
}

.arrow:hover {
    opacity: 0.8;
}

.arrow:focus {
    opacity: 0.8;
}

</style>