<script setup>
import Button from '../components/shared/Button.vue'
import GameRecycleBins from '../components/gameplay/GameRecycleBins.vue';
import Hint from '../components/gameplay/Hint.vue'
import GameGarbage from '../components/gameplay/GameGarbage.vue';
import GoBack from '../components/shared/GoBack.vue'
import ScoreVue from '../components/gameplay/Score.vue';
import FinalScoreVue from '../components/gameplay/FinalScore.vue';
import BackgroundGameVue from '../components/gameplay/BackgroundGame.vue';
import Timer from '../components/gameplay/Timer.vue';
import GameTrashMountain from '../components/gameplay/GameTrashMountain.vue';
import WhyRecycleCardVue from '../components/education/WhyRecycleCard.vue';
</script>

<template>
  <GoBack :isGame=true />
  <WhyRecycleCardVue title="We are big Polluters!" text="The average person throws away 4 pounds of trash every single day. Over a year, that makes about 1.5 tons of waste. Now consider that there are 7 billion people on this planet and you can see why this is a massive environmental problem!
" image="src/assets/education/whyRecycle-img1.jpg" colorCard="yellow" />
  <Button text="Start Game" variant="game" @click="startGame" />
  <div class="recycleBins__grid">
    <GameRecycleBins v-for="bin in recycleBins" :binType="bin" :key="bin" :currentGarbage="currentGarbage"
      @next-garbage="nextGarbage" @wrong-drop="wrongDrop" />
  </div>
  <GameGarbage :setCurrentGarbage="setCurrentGarbage" ref="gameGarbage" />
  <GameTrashMountain ref="gameTrashMountain" />
  <!-- <Hint garbage-name="apple"  garbage-category="organics" /> -->
  <ScoreVue :currentScore="0"></ScoreVue>
  <FinalScoreVue :finalScore="0"></FinalScoreVue>
  <Timer></Timer>
  <BackgroundGameVue :numWrong="3" />
</template>

<script>
export default {
  name: "Sandbox",
  methods: {
    startGame() {
      console.log("Starting game...");
    },
    setCurrentGarbage(garbage) {
      this.currentGarbage = garbage
    },
    nextGarbage() {
      this.$refs.gameGarbage.getRandomGarbage()
    },
    wrongDrop() {
      this.$refs.gameTrashMountain.moveMountainY()
    }
  },
  computed: {},
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
      ]
    };
  }
};
</script>

<style scoped>
main {
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 6rem;
  padding: 5px;
  background-color: white;
}

.recycleBins__grid {
  display: grid;
  grid-template: repeat(2, 1fr)/repeat(3, 1fr);
  grid-gap: 1.25rem;
  place-items: center;
}
</style>
