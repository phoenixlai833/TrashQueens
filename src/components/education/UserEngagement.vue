<script setup>
</script>

<template>
    <div class="component">
        <h1 class="component__title">Ready to make a difference?</h1>
        <p class="component__info">Helpful links and resources</p>
        <div class="card">
            <h2 class="card__header">Recycle BC</h2>
            <div class="card__inner">
                <p class="card__inner__content">Recycle BC is a not-for-profit organization responsible for residential
                    packaging and paper product recycling throughout British Columbia, servicing over two million
                    households or over 99% of BC through curbside, multi-family and/or depot services.</p>
                <a class="card__inner__link" href="https://www.recyclebc.ca/" target="_blank">recyclebc.ca</a>
            </div>
        </div>
        <div class="card">
            <h2 class="card__header">Environment 911</h2>
            <div class="card__inner">
                <p class="card__inner__content">Environment911 was originally launched by the Liski family as a website
                    dedicated to reporting environmental issues caused by consumer consumption and the depletion of
                    non-renewable resources.</p>
                <a class="card__inner__link" href="https://www.environment911.org/"
                    target="_blank">environment911.org</a>
            </div>
        </div>
        <slot></slot>
    </div>
</template>

<script>
export default {
    name: "UserEngagement",
    methods: {},
    computed: {},
    props: {},
    data() {
        return {};
    }
};
</script>

<style scoped>
.component {
    display: flex;
    flex-direction: column;
    background-color: #273D4E;
    font-family: "Nunito-Regular", sans-serif;
    width: 100%;
    padding: 1rem;
    gap: 1.5rem;
    max-width: 390px;
    color: #F5F9E9;
}

.component__title {
    font-family: "FuzzyBubbles-Regular", sans-serif;
    text-align: center;
    font-size: 2rem;
}

.component__info {
    font-size: 1rem;
    text-align: center;
}
.card {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.card__header {
    font-family: "FuzzyBubbles-Regular", sans-serif;
    text-align: start;
    font-size: 1.25rem;
}

.card__inner {
    display: flex;
    flex-direction: column;
    gap: 1rem;
    border: 1px solid #F5F9E9;
    padding: 0.5rem;
}

.card__inner__content {
    text-align: start;
    font-size: 0.875rem;
}

.card__inner__link {
    text-align: end;
    font-size: 1rem;
    color: #F5F9E9;
}
</style>