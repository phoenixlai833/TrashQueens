<template>

  <div class="hintParent">
    <div class="hintBox hintChild" v-if="showHintBox">
      <h3>{{ hintBoxNote }}</h3>
      <div class="hintX hintChild" @click="showHintBox = false">
        <h2>x</h2>
      </div>
    </div>

    <div class="hintButton hintChild" @click="showHintBox = !showHintBox">
      <img src="/assets/idea.png" alt="hint">
    </div>
  </div>

</template>



<script>

export default {
  name: "Hint",
  methods: {},
  computed: {
    hintBoxNote: function () {
      const [NoteObject] = this.listOfNotes
        .filter(listItem => listItem.category === this.garbageCategory)
      return NoteObject.hintNote
    },
  },
  props: {
    garbageName: String,
    garbageCategory: String
  },
  data() {
    return {
      listOfNotes: [
        { category: "organics", hintNote: "This is the purest form of recycling, because nature does 100% of the work for us! " },
        { category: "glass", hintNote: "We can take them and purpose them without any loss in quality." },
        { category: "metal", hintNote: "No pun intended, but some can be used to create new road signs and window frames" },
        { category: "paper", hintNote: "They can be recycled into a whole bunch of new things, including new boxes, paper towels!" },
        { category: "e-waste", hintNote: "They are a treasure trove of recyclable material!" },
        { category: "plastic", hintNote: "They can be recycled into ropes, packaging, chairs, brush bristles and even car bumpers!" },
      ],
      showHintBox: false,
    };
  },
};

</script>


<style scoped>

.hintChild {
  position: absolute;
}

.hintBox {
  bottom: 0;
  left: 0;

  padding: 35px;
  height: 245px;
  width: 320px;
  background-color: #F5F9E9;
  border-radius: 10px 10px 10px 28px;

  display: flex;
  align-items: center;
  justify-content: center;
  font-family: "Nunito-Bold", sans-serif;
  /* z-index: 10000; */
}

.hintX {
  top: 0;
  right: 0;
  height: 60px;
  width: 60px;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  z-index: 20;
}

.hintButton {
  bottom: 0;
  left: 0;

  height: 60px;
  width: 60px;
  background-color: #FFD45D;
  border-radius: 40px;
  box-shadow: 0 1px 1px 1px rgba(0, 0, 0, 0.25);

  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 20;
}

.hintButton img {
  height: 75%;
  width: 75%;
  object-fit: contain
}
</style>


