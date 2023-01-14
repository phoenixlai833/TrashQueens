<script setup >
import FinalScoreVue from '../components/gameplay/FinalScore.vue';
import Button from '../components/shared/Button.vue'
import Iconify from '../components/shared/Iconify.vue';
</script>

<template>
    <div class="container">
        <FinalScoreVue :finalScore="destinationId" />
        <h1>Share your results!</h1>
        <div class="social-sharing__container">
            <a class="social-sharing-link" :href="'https://www.facebook.com/sharer.php?u=' + postUrl">
                <Iconify iconName="icon-park-twotone:facebook" iconColor="#273D4E" iconHeight="40" />
            </a>
            <a class="social-sharing-link" :href="'https://twitter.com/share?url=' + postUrl">
                <Iconify iconName="icon-park-twotone:twitter" iconColor="#273D4E" iconHeight="40" />
            </a>
            <a class="social-sharing-link" :href="'https://pinterest.com/pin/create/bookmarklet/?url=' + postUrl">
                <Iconify iconName="mingcute:pinterest-line" iconColor="#273D4E" iconHeight="40" />
            </a>
        </div>

        <Button text="Play Again" variant="alternate" @click="playAgain" class="btn"></Button>
    </div>
</template>

<script >

export default {
    props: [
        "finalScore"
    ],
    methods: {
        playAgain() {
            this.$router.push("/gameplay-easy");
        }
    },
    data() {
        return {
            postUrl: encodeURI(document.location.href)
        }
    },
    computed: {
        destinationId() {
            return parseInt(this.$route.params.id)
        }
    }
};



</script>

<style scoped>
.container {
    height: 85vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.btn {
    margin: 10px 0;
}

h1 {
    font-family: "FuzzyBubbles-Bold", sans-serif;
    font-size: 1.5rem;
    text-align: center;
}

a {
    text-decoration: none;
}

.social-sharing__container {
    display: flex;
    width: 100%;
    justify-content: space-between;
    padding: 1rem 2rem;
}
</style>