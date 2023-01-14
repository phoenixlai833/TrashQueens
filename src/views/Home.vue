<script setup>
import Card from '../components/home/Card.vue';
import Button from '../components/shared/Button.vue'
import Scroll from '../components/shared/Scroll.vue';
import HeroImage from '../components/home/heroImage.vue';
import GameTitle from '../components/home/GameTitle.vue';
</script>

<template>
  <div class="center">
    <GameTitle />
    <div class="topSec">
      <HeroImage />
      <div class="cta">
        <h2 class="cta__title">Join the Trash Queens</h2>
        <Button text="Quick Play" variant="alternate" @click="startGame" />
        <p class="cta__text">The power to save the world is at your fingertips.</p>
      </div>
    </div>
    <div class="bottomCards">
      <Card :text="gameText" :title="gameTitle" :image="gameImage" cardColor="yellow" :buttonText="gameButtonText"
        :buttonFunction="game" />
      <Card :text="resourceText" :title="resourceTitle" :image="resourceImage" cardColor="red"
        :buttonText="resourceButtonText" :buttonFunction="education" />
      <Card :text="aboutText" :title="aboutTitle" :image="aboutImage" cardColor="blue" :buttonText="aboutButtonText"
        :buttonFunction="about" />
    </div>
    <Scroll />
  </div>
</template>

<script>
export default {
  name: "Home",
  methods: {
    startGame() {
      this.$router.push("/gameplay-easy");
    },
    game() {
      this.$router.push("/game");
    },
    about() {
      this.$router.push("/about");
    },
    education() {
      this.$router.push("/education");
    },
  },
  computed: {},
  props: {},
  data() {
    return {
      gameText: "Help the Trashy Queens sort through the wastes of the endless Trash Mountain!",
      gameTitle: "Explore the Game",
      gameImage: `/assets/recycling-bins/plastic-bin.svg`,
      gameButtonText: "The Game",
      resourceText: "Saving the world requires you to be vigilant. Learn real life skills to tackle the challenges around you!",
      resourceTitle: "Expand your Knowledge",
      resourceImage: `/assets/recycling-bins/organic-bin.svg`,
      resourceButtonText: "Learn More",
      aboutText: "Come and meet the awesome developers who designed and built this game!",
      aboutTitle: "Meet the Team",
      aboutImage: `/assets/recycling-bins/metal-bin.svg`,
      aboutButtonText: "About Us",
    };
  },
  components: {
    Button,
    Scroll,
    Card
  }
};
</script>

<style scoped>
.center {
  height: 100%;
  width: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 1rem;
}

.topSec {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.bottomCards {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.cta {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
  width: 80%;
  max-width: 390px;
}

.cta__title {
  font-size: 1.5rem;
  font-family: "FuzzyBubbles-Bold", sans-serif;
  text-align: center;
}

.cta__text {
  font-size: 1.25rem;
  font-family: "Nunito-Bold", sans-serif;
  text-align: center;
}

@media only screen and (min-width: 768px) {
  /* .topSec {
    display: flex;
    flex-direction: row;
    align-items: center;
  }

  .bottomCards {
    display: flex;
    flex-direction: row;
    align-items: center;
  } */
}
</style>