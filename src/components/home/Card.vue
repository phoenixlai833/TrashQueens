<script setup>
    import Button from '../shared/Button.vue'
</script>

<template>
    <div class="card" :class="cardColor">
        <div class="card__image">
            <img :src="image" alt="Trash Queens are beautiful" />
        </div>
        <div class="card__content">
            <h2 class="card__title">{{ title }}</h2>
            <p class="card__text">{{ text }}</p>
            <Button :text="buttonText" variant="primary" @click="buttonFunction" />
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    methods: {},
    computed: {},
    props: {
        title: {
            type: String,
            required: true
        },
        text: {
            type: String,
            required: true
        },
        buttonText: {
            type: String,
            required: true
        },
        image: {
            type: String,
            required: true
        },
        buttonFunction: {
            type: Function,
            required: true
        },
        cardColor: {
            type: String,
            required: true,
            default: "yellow"
        }
    },
    data() {
        return {};
    }
};
</script>

<style scoped>

    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        border-radius: 8px;
        margin-top: 6rem;
        filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
        width: 90%;
        max-width: 390px;
    }

    .yellow {
        background-color: #F7C932;
    }

    .red {
        background-color: #E05F4E;
    }

    .blue {
        background-color: #84A7F1;
    }

    .card__image {
        position: absolute;
        height: 12rem;
        z-index: 10;
    }

    .card__content {
        width: 100%;
        padding: 2rem 1.5rem;
        gap: 1.5rem;
        margin-top: 5.5rem;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }

    img {
        width: 100%;
        height: 100%;
        translate: 0 -5.5rem;
        object-fit: contain;
        filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.25));
    }

    .card__title {
        font-size: 1.5rem;
        font-weight: 700;
        text-align: center;
        font-family: "FuzzyBubbles-Bold", sans-serif;
    }

    .card__text {
        font-size: 1rem;
        text-align: center;
        font-family: "Nunito-Regular", sans-serif;
        width: 90%;
    }
</style>