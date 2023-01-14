<script setup>
import Button from '../shared/Button.vue'
import Tracker from '../tutorial/Tracker.vue';
import Arrow from '../shared/Arrow.vue';
</script>

<template>
    <div class="card" :class="color">
        <h1 class="card__title">{{ title }}</h1>
        <div class="card__image__row">
            <template v-for="(s, i) in trashSource" :key="i">
                <img class="card__image" :src="s" alt="trash">
            </template>
        </div>
        <p class="card__content">{{ text }}</p>
        <div class="card__arrows">
            <Arrow arrowName="icon-park-twotone:arrow-circle-left" arrowColor="#F5F9E9" :arrowHeight=42 @click="backClick" />
            <Arrow arrowName="icon-park-twotone:arrow-circle-right" arrowColor="#F5F9E9" :arrowHeight=42 @click="forwardClick" />
        </div>
        <div class="card__bottom">
            <p class="card__text">{{ content }}<strong>{{ bin }}</strong></p>
            <img class="card__bin" :src="binSource" alt="bin">
        </div>
        <div class="card__tracker">
            <Tracker :trackerPosition="currentStep" :totalPositions=6 :variant=true />
        </div>
    </div>
</template> 

<script>
export default {
    name: "CarouselCard",
    methods: {},
    computed: {},
    props: {
        title: {
            type: String,
            required: true
        },
        content: {
            type: String,
            required: true
        },
        text: {
            type: String,
            required: true
        },
        trashSource: {
            type: Array,
            required: true
        },
        binSource: {
            type: String,
            required: true
        },
        bin: {
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
        color: {
            type: String,
            required: true
        },
    },
    data() {
        return {};
    },
    components: {
        Arrow,
        Tracker
    }
};
</script>

<style scoped>
.card {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    padding: 1rem;
    border-radius: 20px;
    font-family: "Nunito-Regular", sans-serif;
    color: #273D4E;
    min-height: 600px;
    max-width: 390px;
    min-width: 370px;
}

.blue {
    background-color: #84A7F1;
}

.yellow {
    background-color: #F7C932;
}

.red {
    background-color: #E05F4E;
}

.card__title {
    font-size: 1.5rem;
    font-family: "FuzzyBubbles-Bold", sans-serif;
}

.card__content {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
}

.card__image {
    max-height: 80px;
    max-width: 80px;
    width: 100%;
}

.card__image__row {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    width: 100%;
}

.card__text {
    font-size: 1rem;
    font-family: "Nunito-Regular", sans-serif;
}

.card__arrows {
    display: flex;
    flex-direction: row;
    position: absolute;
    justify-content: space-between;
    width: 100%;
    height: 100%;
}

.card__bottom {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 1.5rem;
}

strong {
    font-family: "Nunito-Bold", sans-serif;
}

.card__bin {
    height: 160px;
}

.card__tracker {
    display: flex;
    justify-content: center;
    align-items: center;
}
</style>