<script setup>
import Iconify from './Iconify.vue'
</script>

<template>
    <div class="scroll" @click="scrollToTop">
        <p class="scroll__text" :color="fontColor">{{ text }}</p>
        <Iconify iconName="icon-park-twotone:up-one" :iconColor="scrollColor" :iconHeight=32 />
    </div>
</template>

<script>
export default {
    name: "Scroll",
    methods: {
        scrollToTop() {
            window.scrollTo({
                top: 0,
                behavior: "smooth"
            });
        }
    },
    computed: {},
    props: {
        navColor: {
            type: String,
            required: false,
            default: "#273D4E"
        },
        fontColor: {
            type: String,
            required: false,
            default: "#273D4E"
        },
        scrollColor: {
            type: String,
            required: false,
            default: "#273D4E"
        }
    },
    data() {
        return {
            text: "Scroll to Top"
        };
    }
};
</script>

<style scoped>
.scroll {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 0.5rem;
    padding: 1rem;
    cursor: pointer;
    transition: all 0.2s ease-in-out;
}

.scroll:hover {
    color: #F7C932;
    transform: translateY(-0.1rem);
}

.scroll__text {
    font-family: "Nunito-Regular", sans-serif;
    font-size: 1rem;
}
</style>