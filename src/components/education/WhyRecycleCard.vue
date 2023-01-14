
<template>
    <div class="card" :class="cardColor">
        <img :src="image" alt="Image text" />
        <h2 class="card__title__text">{{ title }}</h2>
        <p class="card__text">{{ text }}</p>
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
    border-radius: 10px;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
    width: 100%;
    padding: 1.5rem;
    gap: 1rem;
    max-width: 350px;
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
    font-size: 1.5rem;
    font-family: "FuzzyBubbles-Bold", sans-serif;
}

img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    border-radius: 4px;
}

.card__text {
    font-size: 1rem;
    font-family: "Nunito-Regular", sans-serif;
}
</style>