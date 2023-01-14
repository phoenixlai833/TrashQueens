<script setup>
import Button from '../shared/Button.vue'
</script>
<template>
  <div class="overlay">

  </div>
  <div class="promptBox">
    <span>
      <h3>Are you sure you want to quite this awesome game?</h3>
      <div class="promptButtons">
        <button class="stayBtn" @click="stayInGame">Keep Playing</button>
        <button class="leaveBtn" @click="leaveGame">Leave</button>
        <!--          <Button text="Keep Playing" variant="game"  @click="stayInGame" class="stayBtn"></Button>-->
        <!--          <Button text="Leave" variant="alternate" @click= "leaveGame" class="leaveBtn"></Button>-->
      </div>
    </span>
  </div>
</template>

<script>

export default {
  name: "ExitGamePrompt",
  methods: {
    stayInGame() {
      this.$emit('stayInGame');
    },
    leaveGame() {
      this.$router.push("/game");
    }
  },
  computed: {},
  props: {
    openPrompt: String,
  }
  ,
  data() {
    return {};
  },
};

</script>


<style scoped>
.overlay {
  position: fixed;
  top: 0;
  left: 0;

  height: 100vh;
  width: 100vw;
  background-color: #333;
  opacity: 0.8;
  /*backdrop-filter: blur(4rem);*/
  /*filter: blur(2rem);*/
}

.promptBox {
  position: absolute;
  top: 30vh;
  left: 31.5vw;
  /* top:270px;
  left:24px; */

  padding: 50px 35px 35px 35px;
  height: 250px;
  width: 320px;
  background-color: #F5F9E9;
  border-radius: 10px;

  display: flex;
  align-items: center;
  justify-content: center;
  /*backdrop-filter: blur(6rem);*/
  z-index: 1;

}

.promptButtons {
  margin: 1rem 0;
  display: flex;
  /*justify-content: space-around;*/
  justify-content: center;
}

.promptButtons button {
  width: 108px;
  height: 32px;
  margin: 5px;
  border-radius: 8px;
  color: #F5F9E9;
  border: 0;
}

.leaveBtn {
  background-color: #5AB4AB;
}


.stayBtn {
  background-color: #273D4E;
}
</style>


