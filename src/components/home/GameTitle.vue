<template>
    <div class="gameTitle__container">
        <div class="gameTitle__background"></div>
        <img src="/assets/others/game-title.svg" alt="game-title">
    </div>
</template>

<script>
export default {
    name: 'GameTitle',
    method: {},
    computed: {},
    props: {},
    data() {
        return {

        }
    }
}
</script>

<style scoped>
.gameTitle__container {
    width: 100%;
    height: 9.188rem;
    transform: translateY(-.5rem)
}

.gameTitle__background {
    width: 100vw;
    height: 7.1rem;
    background-color: #5AB4AB;
    border-radius: 0 0 40px 40px;
}

img {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;

}
</style>