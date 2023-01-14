<script setup>
import ExitGamePrompt from '../gameplay/ExitGamePrompt.vue';
</script>

<template>
  <div>
    <div class="go-back" @click="backBtnClicked">
      <img src="/assets/back.png" alt="go back">
    </div>
    <ExitGamePrompt @stayInGame="handleCreate" v-if="openPrompt && isGame" />
  </div>
</template>

<script>
export default {
  name: "GoBack",
  methods: {
    backBtnClicked() {
      this.isGame
        ? this.openPrompt = true
        : this.$router.go(-1)
    },
    handleCreate() {
      this.openPrompt = false
    }
  },
  computed: {},
  props: {
    isGame: Boolean,
  },
  data() {
    return {
      openPrompt: false
    };
  }
}
</script>


<style scoped>
.go-back {
  width: 35px;
  height: 30px;
}

img {
  height: 100%;
  width: 100%;
  object-fit: contain
}
</style>