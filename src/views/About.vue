<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
</script>

<template>
  <Header title="About">

    <template class="aboutIntro__content" v-slot:Desc>
      <p>We hope that you enjoy exploring our project as much as we enjoyed making it!</p>
    </template>
  </Header>

  <div class=" card left--card">
    <div class="card__content">
      <h3> Vision </h3>
      <p>We want to provide a quick and fun experience that you can share with others and educate them on how to
        properly dispose of their trash.
      </p>
    </div>
  </div>

  <div class=" card right--card">
    <div class="card__content">
      <h3> Trash Queens </h3>
      <p>We are a team of 4 full-stack web development students that care about the environment and love experimenting
        with code!</p>

    </div>
  </div>

  <div class=" card left--card team--card">
    <div class="card__TM--content ">
      <img src="/assets/profile-photos/phoenix-profile.png" alt="Phoenix Photo">
      <div>
        <h3>Phoenix Lai</h3>
        <p>Full-stack web developer/ designer trying to create a better world, one less single use plastic at a time.
        </p>
        <div class="card__link">
          <a href="https://www.linkedin.com/in/phoenix-lai">LinkedIn</a>
          <a href="https://github.com/phoenixlai833">GitHub</a>
        </div>
      </div>
    </div>
    <div class="card__TM--content ">
      <div class="card__image">
        <img src="/assets/profile-photos/yasmina-profile.avif" alt="Yasmina Photo">
      </div>
      <div>
        <h3>Yasmina Amirifar </h3>
        <p>A passionate web developer who enjoys creating entertaining and cool web apps. </p>
        <div class="card__link">
          <a href="https://www.linkedin.com/in/yasmina-amir-70b88b196/">LinkedIn </a>
        </div>
      </div>
    </div>
    <div class="card__TM--content">
      <img src="/assets/profile-photos/stefanie-profile.jpg" alt="Stefanie Photo">
      <div>
        <h3>Stefanie Taswin</h3>
        <p>An aspiring full-stack web developer. Obsessed with coffee, games, and an explorer.</p>
        <div class="card__link">
          <a href="https://www.linkedin.com/in/callistef/ ">LinkedIn</a>
          <a href="mailto: callistastefanie@gmail.com">Email</a>
        </div>
      </div>
    </div>
    <div class="card__TM--content">
      <img src="/assets/profile-photos/laurent-profile.avif" alt="Laurent Photo">
      <div>
        <h3>Laurent Beique </h3>
        <p>One part web developer and three parts self-critic all wrapped up in a meat Popsicle.</p>
        <div class="card__link">
          <a href="https://www.linkedin.com/in/laurent-beique/">LinkedIn</a>
          <a href="https://github.com/lbeique">GitHub</a>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  name: "About",
  methods: {

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

.card {
  align-items: center;
  position: relative;
  width: 390px;
  margin: 1rem 0 2rem 0;
  padding: 1rem;
  color: #F5F9E9;
  background-color: #5AB4AB;
  filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.15));
}

.left--card {
  transform: translateX(-2.5rem);
  border-radius: 8px;
  padding-left: 50px;
}

.right--card {
  transform: translateX(2.5rem);
  border-radius: 8px;
  padding-right: 50px;
}


.card__content {
  width: 100%;
  padding: .5rem;
  gap: 1.5rem;
}

.card__TM--content {
  display: flex;
  gap: 1.5rem;
  margin-top: 24px;
  padding: .5rem;

}

.card__link {
  display: flex;
  gap: 1rem;
}

a {
  color: #F7C932;
  font-family: "Nunito-Regular", sans-serif;
  font-size: 11px;
}

p {
  font-family: "Nunito-Regular", sans-serif;
}

.card p {
  font-size: 12px;
}

img {
  width: 91px;
  height: 91px;
  object-fit: cover;
  border-radius: 8px;
}


h2 {
  font-family: "FuzzyBubbles-Regular", sans-serif;
  color: #5ab4ab;
  font-size: 1.5rem;
}

h3 {
  font-family: "FuzzyBubbles-Bold", sans-serif;
  font-size: 18px;
  margin-bottom: 5px;

}
</style>
