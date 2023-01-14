<template>
    <div>
        <img draggable="false" class="trashMountain__svg" :style="{ 'transform': `translateY(${translateRem}rem)` }"
            src="/assets/garbages/trash-mountain.svg" alt="trash-mountain" />
        <!-- <button @click="moveMountainY()">move up </button> -->
    </div>
</template>

<!-- 
    <br>
<div align="center">
  <img src="https://github.com/CalliStef/Callista-Lucia/blob/gh-pages/assets/images/13_prototype_mockup_complete_vid.gif?raw=true" alt="Prototype_Final_Video" width="400" height="200">
</div> 
<br>
 -->

<script>
export default {
    name: 'GameTrashMountain',
    components: {},
    methods: {
        moveMountainY() {
            if (this.counter < 9) {
                this.counter++
                this.translateRem = this.translateRem - 1.3
                this.$emit("wrongItems", this.counter)
                this.setWrongNums(this.counter)
            } else {
                this.$router.push(`/result/${this.finalScore}`)
            }
        }
    },
    computed: {},
    props: {
        setWrongNums: Function,
        finalScore: Number
    },
    data() {
        return {
            translateRem: 0,
            counter: 0
        }
    }
}

</script>

<style scoped>
.trashMountain__svg {
    /* width: 24.375rem; */
    width: 100%;
    height: 16.5rem;
    transition: all .2s;
    /* z-index: -10; */

}
</style>