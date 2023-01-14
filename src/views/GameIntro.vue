<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
import GameButtonMode from '../components/gameIntro/GameButtonMode.vue';
</script>

<template>
  <Header title="Start Game">
    <template v-slot:Button>
      <Button text="Tutorial" variant="tutorial-alternate" @click="startTutorial" />
    </template>
  </Header>

  <div class="gameIntro__content">
    <h2>So you think you can recycle?</h2>
    <p>Try your hand at our game by playing through different levels in order to test your knowledge!</p>
  </div>

  <RouterLink style="text-decoration: none;" to="/gameplay-easy">
    <GameButtonMode :gameMode="'easy'" />
  </RouterLink>
  <RouterLink style="text-decoration: none;" to="/gameplay-hard">
    <GameButtonMode :gameMode="'hard'" />
  </RouterLink>



</template>

<script>
export default {
  name: "GameIntro",
  methods: {
    startTutorial() {
      this.$router.push("/tutorial");
    }
  },
  computed: {},
  props: {},
  data() {
    return {};
  },
  components: {
    Header,
    Button
  }
};
</script>

<style scoped>
.header {
  padding: 2rem;
}

.gameIntro__content {
  display: flex;
  flex-direction: column;
  align-content: center;
  row-gap: 1rem;
  margin: 3rem 2rem;
}

h2 {
  font-family: "FuzzyBubbles-Regular", sans-serif;
  color: #5ab4ab;
  font-size: 1.25rem;
  text-align: center;
}

p {
  font-family: "Nunito-Regular", sans-serif;
  color: black;
  font-size: 0.938rem;
  text-align: center;
}
</style>
