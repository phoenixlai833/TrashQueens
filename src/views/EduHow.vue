<script setup>
import Button from '../components/shared/Button.vue'
import { RouterLink, RouterView } from 'vue-router'
import Header from '../components/shared/Header.vue';
import UserEngagement from '../components/education/UserEngagement.vue';
import Scroll from '../components/shared/Scroll.vue';
import Carousel from '../components/education/Carousel.vue';
</script>

<template>
  <Header title="How to Recycle?" />
  <div class="page">
    <Carousel />
  </div>
</template>

<script>
export default {
  name: "EduHow",
  methods: {

  },
  computed: {


  },
  props: {


  },
  data() {
    return {


    };
  },
  components: {
    Header,
    Carousel
  }
};
</script>

<style scoped>
.header {
  padding: 1rem 2rem;
}

.page {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1rem 0.5rem;
  width: 100%;
}
</style>