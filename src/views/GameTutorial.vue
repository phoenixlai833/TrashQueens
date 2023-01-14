<script setup>
import Button from '../components/shared/Button.vue';
import GoBack from '../components/shared/GoBack.vue';
import Tutorial from '../components/tutorial/Tutorial.vue';
</script>

<template>
    <div class="page">
        <GoBack />
        <Tutorial v-if="position == 1" :currentStep="position" :text="firstText" :imageSource="firstImgUrl"
            backText="Return" forwardText="Next" :backClick="handleReturn" :forwardClick="handlePageTwo" />
        <Tutorial v-if="position == 2" :currentStep="position" :text="secondText" :imageSource="secondImgUrl"
            backText="Previous" forwardText="Next" :backClick="handlePageOne" :forwardClick="handlePageThree" />
        <Tutorial v-if="position == 3" :currentStep="position" :text="thirdText" :imageSource="thirdImgUrl"
            backText="Previous" forwardText="Start Game" :backClick="handlePageTwo" :forwardClick="handleGameStart" />
    </div>
</template>

<script>
export default {
    name: "Tutorial",
    methods: {
        handleReturn() {
            this.$router.push("/game");
        },
        handlePageOne() {
            this.position = 1;
        },
        handlePageTwo() {
            this.position = 2;
        },
        handlePageThree() {
            this.position = 3;
        },
        handleGameStart() {
            this.$router.push("/gameplay-easy");
        }
    },
    computed: {},
    props: {},
    data() {
        return {
            position: 1,
            firstText: "In this game, you will be helping the Trash Queens by sorting and recycling trash.",
            firstImgUrl: "assets/tutorial/tutorial1.png",
            secondText: "The goal of the game is to sort as much trash as you can into one of 6 recycling bins. You can do this by dragging and dropping the trash into a bin.",
            secondImgUrl: "assets/tutorial/tutorial2.png",
            thirdText: "You will be given a score based on how much trash you sort correctly in under a minute. Your score will be displayed at the end of the game. Good luck!",
            thirdImgUrl: "assets/tutorial/tutorial3.png",
        }
    },
    components: {
        GoBack,
        Button,
        Tutorial
    }
};
</script>

<style scoped>
.page {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 2rem;
    gap: 2rem;
    width: 100%;
}
</style>