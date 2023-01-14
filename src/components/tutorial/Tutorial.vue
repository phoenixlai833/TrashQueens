<script setup>
import Button from '../shared/Button.vue'
import Tracker from './Tracker.vue';
</script>

<template>
    <div class="card">
        <div class="placeholder"></div>
        <div class="card__content">
            <h1 class="card__title">Tutorial</h1>
            <div class="card__content--left">
                <img class="card__image" :src="imageSource" alt="image" />
            </div>
            <div class="card__content--right">
                <h1 class="card__title_small">Tutorial</h1>
                <p class="card__text">{{ text }}</p>
                <div class="card__buttons">
                    <Button :text="backText" variant="tutorial" @click="backClick" />
                    <Button :text="forwardText" variant="tutorial" @click="forwardClick" />
                </div>
            </div>

        </div>
        <div class="card__tracker">
            <Tracker :trackerPosition="currentStep" :totalPositions=3 />
        </div>
        <!-- <h1 class="card__title">Tutorial</h1>
        <div class="card__content">
            <img class="card__image" :src="imageSource" alt="image">
            <p class="card__text">{{ text }}</p>
        </div>
        <div class="card__buttons">
            <Button :text="backText" variant="tutorial" @click="backClick" />
            <Button :text="forwardText" variant="tutorial" @click="forwardClick" />
        </div>
        <div class="card__tracker">
            <Tracker :trackerPosition="currentStep" :totalPositions=3 />
        </div> -->
    </div>
</template> 

<script>
export default {
    name: "Tutorial",
    methods: {},
    computed: {},
    props: {
        text: {
            type: String,
            required: true
        },
        imageSource: {
            type: String,
            required: true
        },
        backText: {
            type: String,
            required: true
        },
        forwardText: {
            type: String,
            required: true
        },
        backClick: {
            type: Function,
            required: true
        },
        forwardClick: {
            type: Function,
            required: true
        },
        currentStep: {
            type: Number,
            required: true
        },
    },
    data() {
        return {};
    },
    components: {
        Button,
        Tracker
    }
};
</script>

<style scoped>
.card {
    width: 100%;
    min-height: 622px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    background-color: #273D4E;
    padding: 3rem;
    border-radius: 20px;
}

.card__title,
.card__title_small {
    color: #F5F9E9;
    font-size: 1.5rem;
    font-family: "FuzzyBubbles-Bold", sans-serif;
}

.card__title_small {
    display: none;
}

.card__content {
    /* mobile */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 1rem;
    max-width: 230px;
}

.card__content--right {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    /* height: 100%; */
}

@media (min-width: 768px) {

    .card__content {
        flex-direction: row;
        max-width: 900px;
        gap: 3rem;
    }

    .card__title {
        display: none;
    }

    .card__title_small {
        display: block;
    }

    .card__content--right {
        display: flex;
        flex-direction: column;
        justify-content: end;
        height: 300px;
        width: 200px;
        gap: 2rem;
    }

    .card__image {
        max-height: 50vh;
        min-height: 400px;
    }

}


.card__image {
    width: 100%;
    object-fit: cover;
    border-radius: 4px;
}

.card__text {
    color: #F5F9E9;
    font-size: 1rem;
    font-family: "Nunito-Regular", sans-serif;
    margin-bottom: 2rem;
}

.card__buttons {
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.card__tracker {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 3rem;
}
</style>