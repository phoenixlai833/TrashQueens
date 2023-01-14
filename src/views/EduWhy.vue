<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
import UserEngagement from '../components/education/UserEngagement.vue';
import Scroll from '../components/shared/Scroll.vue';
import WhyRecycleCardVue from "../components/education/WhyRecycleCard.vue";
</script>

<template>
  <Header title="Why Recycle?" />
  <WhyRecycleCardVue title="We are big Polluters!" text="The average person throws away 4 pounds of trash every single day. Over a year, that makes about 1.5 tons of waste. Now consider that there are 7 billion people on this planet and you can see why this is a massive environmental problem!
" image="/assets/education/whyRecycle-img1.jpg" cardColor="yellow" />
  <h2>The good news, is that about 75% of our trash can be recycled!</h2>
  <WhyRecycleCardVue title="What is Recycling?" text="So what is recycling? Recycling is a way to use waste and materials, and convert them into new products, so that our waste can be used again. So every time we recycle, we save our environment a little more. All products require more energy and natural resources to produce the very first time.
" image="/assets/education/whyRecycle-img2.jpg" cardColor="red" />
  <h2>Every ton of paper recycled saves 17 trees!</h2>
  <WhyRecycleCardVue title="We must work Together!" text="This is a global issue and we must all play a part in solving it. So spread the word! Share this app and tell your friends and family about the importance of recycling. And the next time you have to dispose of waste, think like a Trash Queen and dispose it in the right bin!
" image="/assets/education/whyRecycle-img3.jpg" cardColor="blue" />
  <h2>Let's create a better future together!</h2>
  <UserEngagement>
    <Scroll scrollColor="#F5F9E9" fontColor="#F5F9E9" />
  </UserEngagement>
</template>

<script>
export default {
  name: "EduWhy",
  methods: {},
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

h2 {
  font-size: 1.5rem;
  font-family: "FuzzyBubbles-bold", sans-serif;
  text-align: center;
  max-width: 350px;
  margin: 50px 0;
}
</style>

