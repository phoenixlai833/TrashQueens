<script setup>
import BackgroundGameVue from '../components/gameplay/BackgroundGame.vue';
import ScoreVue from '../components/gameplay/Score.vue';
import TimerVue from '../components/gameplay/Timer.vue';
import GameRecycleBinsVue from '../components/gameplay/GameRecycleBins.vue';
import GameGarbageVue from '../components/gameplay/GameGarbage.vue';
import HintVue from '../components/gameplay/Hint.vue';
import GameTrashMountain from "../components/gameplay/GameTrashMountain.vue"
</script>

<template>
    <ScoreVue :currentScore="score" :livesLeft="lives" class="topScore" />
    <div class="blueBack">
        <div class="pattern"></div>
        <!-- <img class="pattern" src="/assets/backgrounds/trashpattern.svg" /> -->
    </div>
    <div class="gameContainer">
        <div class="skyArea">
            <BackgroundGameVue ref="backgroundGame" />
            <TimerVue class="timer" :finalScore="score" ref="timerVue" />
        </div>
        <GameTrashMountain class="trashMountain" ref="gameTrashMountain" :setWrongNums="setWrongNums"
            :finalScore="score" />
        <div class="grassArea">
            <div class="recycleBins__grid">
                <GameRecycleBinsVue v-for="bin in recycleBins" :binType="bin" :key="bin"
                    :currentGarbage="currentGarbage" @next-garbage="nextGarbage" @wrong-drop="wrongDrop" />
            </div>
            <GameGarbageVue :setCurrentGarbage="setCurrentGarbage" ref="gameGarbage" class="garbage" />
            <HintVue :garbage-name="currentGarbage.garbageName" :garbage-category="currentGarbage.garbageCategory"
                class="hint" />
        </div>
    </div>
</template>

<script>
export default {
    name: "gameplay-Easy",
    methods: {
        setCurrentGarbage(garbage) {
            this.currentGarbage = garbage
        },
        nextGarbage() {
            this.$refs.gameGarbage.getRandomGarbage()
            this.rounds++
            // console.log("add round", this.rounds)
        },
        wrongDrop() {
            this.$refs.gameTrashMountain.moveMountainY()
            this.$refs.backgroundGame.changeBack(this.numWrong)
        },
        setWrongNums(counter) {
            this.numWrong = counter
            console.log("this is in the gameplay", this.numWrong)
        }
    },
    computed: {
        score() {
            return this.rounds - this.numWrong
        },
        lives() {
            return 9 - this.numWrong
        }
    },
    props: {},
    data() {
        return {
            currentGarbage: {},
            recycleBins: [
                'organics',
                'glass',
                'metal',
                'paper',
                'e-waste',
                'plastic'
            ],
            numWrong: 0,
            rounds: 0
        };
    },
    beforeRouteLeave(to, from) {
        this.$refs.timerVue.clearTimer()
    }
}

</script>

<style scoped>
.blueBack {
    position: absolute;
    top: 0;
    left: 0;
    background-color: #5AB4AB;
    width: 100vw;
    height: 100%;
    opacity: 50%;
}

.pattern {
    background-image: url("/assets/backgrounds/trashpattern.svg");
    filter: invert(91%) sepia(16%) saturate(130%) hue-rotate(38deg) brightness(110%) contrast(95%);
    opacity: 50%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
    width: 100vw;
    height: 100vh;
}

/* .pattern {
    filter: invert(91%) sepia(16%) saturate(130%) hue-rotate(38deg) brightness(110%) contrast(95%);
    opacity: 50%;
    height: 100vh;
    position: absolute;
    top: 0;
    left: 0;
} */

.topScore {
    position: fixed;
    z-index: 10;
}

.trashMountain {
    position: absolute;
    top: 300px;
}

.timer {
    position: absolute;
    top: 36%;
    left: 30%;
    z-index: 1;
}

.gameContainer {
    background-color: #82CE9B;
    height: 100vh;
    width: 390px;
    display: flex;
    flex-direction: column;
    align-items: center;
    /* z-index: -5; */
    /* overflow-y: hidden; */
}

.grassArea {
    background-color: #82CE9B;
    width: 100%;
    height: 100%;
    /* min-height: 500px; */
    /* z-index: 1; */
}

.recycleBins__grid {
    display: grid;
    grid-template: repeat(2, 1fr)/repeat(3, 1fr);
    grid-gap: 1.25rem;
    place-items: center;
    margin: 5% 0;
}

.garbage {
    margin: 20%;
}

.hint {
    position: absolute;
    z-index: 3;
    bottom: 25%;
    left: 10%;
}
</style>

