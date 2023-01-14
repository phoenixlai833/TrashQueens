
<template>
    <div>
        <!-- <svg class="backgroundContainer">
        </svg> -->
        <!-- <img src="`../assets/backgrounds/{{backgrounds[0]}}`" alt="cartoon trees"> -->
        <img :src="backgroundUrl" alt="cartoon trees">

    </div>
</template>

<script>
export default {
    name: "BackgroundGame",
    props: [
        "numWrong"
    ],
    data() {
        return {
            // show: true,
            backgrounds: [
                "Game-Skyscape.svg",
                "Game-Skyscape_orange.svg",
                "Game-Skyscape_dark.svg"
            ],
            backgroundUrl: ""
        }
    },
    methods: {
        changeBack(n) {
            if (n <= 3) {
                this.backgroundUrl = `/assets/backgrounds/${this.backgrounds[0]}`
            } else if (3 < n < 7) {
                this.backgroundUrl = `/assets/backgrounds/${this.backgrounds[1]}`
            }

            if (n >= 7) {
                this.backgroundUrl = `/assets/backgrounds/${this.backgrounds[2]}`
            }
        }
    },
    beforeMount() {
        this.backgroundUrl = `/assets/backgrounds/${this.backgrounds[0]}`

    }

};
</script>

<style scoped>
img {
    width: 100%
}

/* .backgroundContainer {
    background-image: url("../assets/backgrounds/Game-Skyscape.svg");
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 100vw;
    height: 50vh;
} */
</style>