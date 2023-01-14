<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
import UserEngagement from '../components/education/UserEngagement.vue';
import Scroll from '../components/shared/Scroll.vue';
</script>

<template>
  <Header title="Reduce, Reuse, and Recycle" />
  <div class="card column yellow">
    <img class="full" src="/assets/education/altToRecycle-img1.jpg" alt="Image text" />
    <h2 class="card__title__text">Reduce</h2>
    <p class="card__text">Cut back on the amount of trash we generate. It’s
      the best method for keeping the environment
      clean. Less waste to begin means there’s less
      waste for you to clean up!</p>
  </div>
  <div class="card column red">
    <div class="cardSub">
      <div class="second"></div>
      <div class="space"></div>
      <div>
        <h2 class="card__title__text">Reuse</h2>
        <p class="card__text">Finding new ways to use
          things that otherwise
          would have been thrown
          out</p>
      </div>
    </div>
    <div class="cardSub">
      <p class="card__text">Can’t find a way to reuse
        your old stuff? You can
        also donate them to
        someone who needs it.
        Your thrown away item
        can be someone else’s
        take home!</p>
      <div class="space"></div>
      <div class="third"></div>
    </div>
  </div>
  <div class="card blue">
    <div>
      <h2 class="card__title__text">Recycle</h2>
      <p class="card__text">Turn something old and
        useless (like plastic milk
        jugs) intor something new
        useful (like picnic benches
        and recycling bins).
        Instead of throwing them
        out, let’s try to recycle
        them instead!</p>
    </div>
    <div class="fourth"></div>
  </div>
  <UserEngagement>
    <Scroll scrollColor="#F5F9E9" fontColor="#F5F9E9" />
  </UserEngagement>

</template>

<script>
export default {
  name: "EduAlt",
  methods: {

  },
  computed: {},
  props: {},
  data() {
    return {};
  },
  components: {
    Header,
    Button,
    UserEngagement
  }
};
</script>

<style scoped>
.header {
  padding: 2rem;
}

.card {
  display: flex;
  border-radius: 10px;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
  width: 100%;
  padding: 1.5rem;
  gap: 1rem;
  max-width: 350px;
  margin-bottom: 40px;
}

.space {
  width: 50px;
}

.column {
  flex-direction: column;
}

.cardSub {
  display: flex;
}

.yellow {
  background-color: #F7C932;
}

.red {
  background-color: #E05F4E;
}

.blue {
  background-color: #84A7F1;
}

.card__title__text {
  font-size: 1.5rem;
  font-family: "FuzzyBubbles-Bold", sans-serif;
}

.full {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.half {
  width: 40%;
  height: 100%;
  object-fit: cover;
  border-radius: 4px;
}

.second {
  background-image: url("/assets/education/altToRecycle-img2.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 100%;
}

.third {
  background-image: url("/assets/education/altToRecycle-img3.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 200%;
}

.fourth {
  background-image: url("/assets/education/altToRecycle-img4.jpg");
  background-position: center;
  background-size: cover;
  background-repeat: no-repeat;
  width: 350%;
}


.card__text {
  font-size: 1rem;
  font-family: "Nunito-Regular", sans-serif;
}
</style>