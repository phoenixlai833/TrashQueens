<script setup>
import Button from '../shared/Button.vue'
</script>

<template>
    <div class="card" :class="cardColor">
        <div class="card__title">
            <h2 class="card__title__text">{{ title }}</h2>
        </div>
        <div class="card__container">
            <div class="card__image">
                <img :src="image" alt="Image text" />
            </div>
            <div class="card__content">
                <p class="card__text">{{ text }}</p>
                <Button text="See More" variant="education" @click="handleClick" />
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "EducationCard",
    methods: {},
    computed: {},
    props: {
        title: {
            type: String,
            required: true,
            default: "Title"
        },
        text: {
            type: String,
            required: true,
            default: "This is a default text"
        },
        image: {
            type: String,
            required: true
        },
        handleClick: {
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
    border-radius: 8px;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
    width: 100%;
    padding: 1rem;
    gap: 1rem;
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
.card__title__text {
    font-size: 1.25rem;
    font-family: "FuzzyBubbles-Regular", sans-serif;
}

.card__image {
    min-width: 120px;
    max-width: 120px;
    min-height: 120px;
    max-height: 120px;
    
}

img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 4px;
}

.card__container {
    width: 100%;
    display: flex;
    flex-direction: row;
    gap: 1rem;
}

.card__content {
    width: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
}

.card__text {
    font-size: 1rem;
    font-family: "Nunito-Regular", sans-serif;
}
</style>