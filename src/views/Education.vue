<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
import EducationCard from '../components/education/EducationCard.vue';
</script>

<template>
  <div class="page">
    <Header title="Education">
      <template v-slot:Desc>
        <p>Use our resources to further educate your friends and family.</p>
      </template>
    </Header>
    <EducationCard title="Why Recycle?" text="Recycling is the most important thing you can do! Ever!"
      :handleClick="eduWhy" cardColor="yellow" :image="whyUrl" />
    <EducationCard title="How to Recycle?" text="Recycling is the most important thing you can do! Ever!"
      :handleClick="eduHow" cardColor="red" :image="howUrl" />
    <EducationCard title="Recycling Alternatives" text="Recycling is the most important thing you can do! Ever!"
      :handleClick="eduAlt" cardColor="blue" :image="altUrl" />
  </div>
</template>

<script>
export default {
  name: "Education",
  methods: {
    eduWhy() {
      this.$router.push("/edu-why");
    },
    eduHow() {
      this.$router.push("/edu-how");
    },
    eduAlt() {
      this.$router.push("/edu-alt");
    },
  },
  computed: {},
  props: {},
  data() {
    return {
      whyUrl: new URL('https://images.unsplash.com/flagged/photo-1585324853527-1c567d53bb72?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1224&q=80').href,
      howUrl: new URL('https://images.unsplash.com/photo-1503596476-1c12a8ba09a9?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80').href,
      altUrl: new URL('https://images.unsplash.com/photo-1525695230005-efd074980869?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=987&q=80').href,
    };
  },
  components: {
    Header,
    Button,
    EducationCard
  }
};
</script>

<style scoped>
.page {
  display: flex;
  flex-direction: column;
  align-items: center;
  height: 100%;
  width: 100%;
  padding: 2rem;
  gap: 1rem;
}

p {
  font-family: "Nunito-Regular", sans-serif;
}
</style>