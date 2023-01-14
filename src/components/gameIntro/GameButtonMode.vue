<template>

  <template v-if="gameMode === 'easy'">
    <div class="gameMode__button--left">
      <div class="gameMode__container--blue">
        <div class="gameMode__img--easy">
          <img src="/assets/garbages/trash-apple.svg" alt="trash-apple" />
        </div>
        <div class="gameMode__content--easy">
          <h1>EASY</h1>
          <h3>mode</h3>
          <p>
            New here? Try out the easy mode here to learn how
            the game works!
          </p>
        </div>
      </div>
    </div>
  </template>

  <template v-else-if="gameMode === 'hard'">
    <div class="gameMode__button--right">
      <div class="gameMode__container--yellow">
        <div class="gameMode__content--hard">
          <h1>HARD</h1>
          <h3>mode</h3>
          <p>
            Looking for a challenge? Then try your best in this mode!
          </p>
        </div>
        <div class="gameMode__img--hard">
          <img src="/assets/garbages/trash-apple-bitten.svg" alt="trash-apple" />
        </div>
      </div>
    </div>
  </template>

  <!-- </div> -->
</template>

<script>
export default {
  name: "GameButtonMode",
  components: {},
  methods: {},
  computer: {},
  props: ["gameMode"],
  data() {
    return {};
  },
};
</script>

<style scoped>
[class^=gameMode__button] {
  display: flex;
  align-items: flex-end;
  position: relative;
  width: 21.875rem;
  height: 10.125rem;
  margin-top: 2rem;
}

.gameMode__button--left {
  align-self: flex-start;
  transform: translateX(-2.5rem);
}

.gameMode__button--right {
  align-self: flex-end;
  transform: translateX(2.5rem);
}

[class^="gameMode__container"] {
  display: flex;
  flex-direction: row;
  width: 100%;
  height: 7.5rem;
  border-radius: 1.25rem;
  padding: 1rem;
  transition: all .2s;
}

[class^="gameMode__container"]:hover {
  transform: translateY(-0.4rem);
  box-shadow: 0 0.4rem 5px #cac2b8;
}

[class^="gameMode__container"]:active {
  transform: translateY(-0.2rem);
  box-shadow: 0 0.2rem 5px #cac2b8;
}

.gameMode__container--blue {
  background-color: #5ab4ab;
}

/* .gameMode__container--blue:hover {
    transform: translateX(.5rem);
} */

.gameMode__container--yellow {
  background-color: #F7C932;
}

/* .gameMode__container--yellow:hover {
    transform: translateX(-.5rem);
} */

[class^="gameMode__img"] {
  display: flex;
  /* width: 40%; */
  width: 5.625rem;
  height: 6.625rem;
  margin-left: 2rem;
  margin-right: 5rem;
  transform: translateY(-4rem);
}

[class^="gameMode__content"] {
  display: flex;
  flex-direction: column;
}


/* EASY MODE CONTENT */
.gameMode__content--easy>h1 {
  display: flex;
  width: 90%;
  justify-content: end;
  transform: translateY(-3.5rem);
  color: #F7C932;
}

.gameMode__content--easy>h1::after {
  content: 'EASY';
  -webkit-text-stroke: 9px #5ab4ab;
  color: #5ab4ab;
  position: absolute;
  z-index: -1
}


.gameMode__content--easy>h3 {
  display: flex;
  width: 90%;
  justify-content: end;
  color: #F7C932;
}

.gameMode__content--easy>p {
  color: white;
}

/* HARD MODE CONTENT */
.gameMode__content--hard>h1 {
  display: flex;
  justify-content: end;
  transform: translateY(-3.5rem);
  color: #5ab4ab;
}

.gameMode__content--hard>h1::after {
  content: 'HARD';
  -webkit-text-stroke: 9px #F7C932;
  color: #F7C932;
  position: absolute;
  z-index: -1
}

.gameMode__content--hard>h3 {
  display: flex;
  justify-content: end;
  width: 100%;
  color: #5ab4ab;

}

.gameMode__content--hard>p {
  color: black;
}


img {
  position: absolute;
  width: 5.625rem;
  height: 6.625rem;
}

h1 {
  font-family: "FuzzyBubbles-Bold", sans-serif;
  position: absolute;
  font-size: 4rem;
}

h3 {
  font-family: "FuzzyBubbles-Regular", sans-serif;
  font-size: 1.5rem;
}

p {
  font-family: "Nunito-Regular", sans-serif;
  font-size: 0.813rem;
}
</style>
