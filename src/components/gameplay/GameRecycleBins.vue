<template>
  <div class="recycleBin__container" :class="[
    isDrag ? 'dragEnter' : '',
    isRight ? 'isRight' : '',
    isWrong ? 'isWrong' : ''
  ]" @drop="onDrop(binType)" @dragover.prevent>
    <template v-if="binType == 'organics'">
      <img src="/assets/recycling-bins/organic-bin.svg" alt="organic-bin" draggable="false" />
    </template>
    <template v-else-if="binType == 'glass'">
      <img src="/assets/recycling-bins/glass-bin.svg" alt="glass-bin" draggable="false" />
    </template>
    <template v-else-if="binType == 'metal'">
      <img src="/assets/recycling-bins/metal-bin.svg" alt="metal-bin" draggable="false" />
    </template>
    <template v-else-if="binType == 'paper'">
      <img src="/assets/recycling-bins/paper-bin.svg" alt="paper-bin" draggable="false" />
    </template>
    <template v-else-if="binType == 'e-waste'">
      <img src="/assets/recycling-bins/e-waste-bin.svg" alt="e-waste-bin" draggable="false" />
    </template>
    <template v-else-if="binType == 'plastic'">
      <img src="/assets/recycling-bins/plastic-bin.svg" alt="plastic-bin" draggable="false" />
    </template>
    <p>{{ binType.toUpperCase() }}</p>
  </div>
</template>

<script>
export default {
  name: "GameRecycleBin",
  components: {},
  methods: {
    onDrop(binType) {
      if (binType === this.currentGarbage.garbageCategory) {
        this.isRight = true
      } else {
        this.isWrong = true
        this.$emit('wrong-drop')
      }
      setTimeout(() => {
        this.isRight = false
        this.isWrong = false
      }, 1000)
      this.$emit('next-garbage')
    },
    // onDragEnter() {
    //   console.log("enter");
    //   this.isDrag = true;
    // },
    // onDragLeave() {
    //   console.log("leave");
    //   this.isDrag = false;
    // },
  },
  computed: {},
  props: {
    binType: String,
    currentGarbage: Object,
  },
  data() {
    return {
      isDrag: false,
      isWrong: false,
      isRight: false
    };
  },
};
</script>

<style scoped>
.recycleBin__container {
  display: flex;
  width: 6.25rem;
  height: 6.5rem;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 0.938rem;
  padding: 1rem;
  background-color: #fff5e9;
  transition: all 0.2s;
}

.dragEnter {
  transform: translateY(-0.2rem);
  box-shadow: 0 0.2rem 2px #cac2b8;
}

.isRight {
  background-color: #A4FFA7;
}

.isWrong {
  background-color: #FFAFA4;
  animation: shake 0.82s cubic-bezier(.36, .07, .19, .97) both;
}

p {
  font-family: "FuzzyBubbles-Regular", sans-serif;
  font-size: 0.813rem;
  color: black;
  font-weight: bold;
}

img {
  width: 100%;
  height: 100%;
}

@keyframes shake {

  10%,
  90% {
    transform: translate3d(-1px, 0, 0);
  }

  20%,
  80% {
    transform: translate3d(2px, 0, 0);
  }

  30%,
  50%,
  70% {
    transform: translate3d(-4px, 0, 0);
  }

  40%,
  60% {
    transform: translate3d(4px, 0, 0);
  }
}
</style>
