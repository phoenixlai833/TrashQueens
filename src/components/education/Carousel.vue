// vue carousel component that imports the CarouselCard
<script setup>
import CarouselCard from './CarouselCard.vue';
</script>

<template>
    <div class="carousel">
        <template v-for="(card, index) in cards" :key="index">
            <TransitionGroup name="slide">
                <CarouselCard v-if="(index === position)" 
                    :text="card.text" 
                    :color="card.color"
                    :trashSource="card.trashSource" 
                    :binSource="card.binSource" 
                    :content="card.content" 
                    :bin="card.bin"
                    :title="card.title" 
                    :backClick="backClick" 
                    :forwardClick="forwardClick"
                    :currentStep="(position + 1)" />
            </TransitionGroup>
        </template>
    </div>
</template>

<script>
export default {
    name: "Carousel",
    methods: {
        backClick() {
            // modular arithmetic to loop back to the end of the array
            this.position = (this.position + 5) % this.cards.length;
            console.log(this.position)
        },
        forwardClick() {
            this.position = (this.position + 1) % this.cards.length;
            console.log(this.position)
        }
    },
    computed: {

    },
    props: {},
    data() {
        return {
            cards: [
                {
                    title: "Organic",
                    text: "Organics are food waste products or any material that is biodegradable. This is the purest form of recycling, because nature does 100% of the work for us!",
                    trashSource: ['/assets/garbages/trash-apple-bitten.svg', '/assets/garbages/trash-pizza.svg', '/assets/garbages/trash-avocado.svg'],
                    binSource: '/assets/recycling-bins/organic-bin.svg',
                    color: "blue",
                    content: "When you are playing Trash Queens, you need to toss organic waste into the ",
                    bin: "Green Bin"
                },
                {
                    title: "Glass",
                    text: "Glass is infinitely recyclable! We can take bottles, and other common household items, and purpose them without any loss in quality.",
                    trashSource: ['/assets/garbages/trash-glass.svg', '/assets/garbages/trash-broken-bottle.svg', '/assets/garbages/trash-broken-glass.svg'],
                    binSource: '/assets/recycling-bins/glass-bin.svg',
                    color: "yellow",
                    content: "When you are playing Trash Queens, you need to toss glass waste into the ",
                    bin: "Blue Bin"
                },
                {
                    title: "Metal",
                    text: "Metal rocks! No pun intended, but recycling aluminum containers can be used to create new road signs and window frames, that’s super cool!",
                    trashSource: ['/assets/garbages/trash-can.svg', '/assets/garbages/trash-frying-pan.svg', '/assets/garbages/trash-fork.svg'],
                    binSource: '/assets/recycling-bins/metal-bin.svg',
                    color: "red",
                    content: "When you are playing Trash Queens, you need to toss metal wastes into the ",
                    bin: "Yellow Bin"
                },
                {
                    title: "Paper",
                    text: "Paper packaging can be recycled into a whole bunch of new things, including new boxes, paper towels, tissues, plant pot, Kraft paper and even drywall liner!",
                    trashSource: ['/assets/garbages/trash-cardbox.svg', '/assets/garbages/trash-airplane.svg', '/assets/garbages/trash-newspaper.svg'],
                    binSource: '/assets/recycling-bins/paper-bin.svg',
                    color: "blue",
                    content: "When you are playing Trash Queens, you need to toss paper waste into the ",
                    bin: "Teal Bin"
                },
                {
                    title: "E-Waste",
                    text: "Did you know our everyday electronics contain plastics, glass, gold, silver, copper and aluminum? E-wastes are a treasure trove of recyclable material!",
                    trashSource: ['/assets/garbages/trash-mouse.svg', '/assets/garbages/trash-hairdryer.svg', '/assets/garbages/trash-computer.svg'],
                    binSource: '/assets/recycling-bins/e-waste-bin.svg',
                    color: "yellow",
                    content: "When you are playing Trash Queens, you need to toss e-waste into the ",
                    bin: "Red Bin"
                },
                {
                    title: "Plastic",
                    text: "It’s not only plastic containers, but most flexible plastics can be recycled too! Plastic can be recycled into ropes, packaging, chairs, brush bristles and even car bumpers!",
                    trashSource: ['/assets/garbages/trash-cup.svg', '/assets/garbages/trash-bottle.svg', '/assets/garbages/trash-bag.svg'],
                    binSource: '/assets/recycling-bins/plastic-bin.svg',
                    color: "red",
                    content: "When you are playing Trash Queens, you need to toss plastic waste into the ",
                    bin: "Purple Bin"
                }
            ],
            position: 0
        };
    },
    components: {
        CarouselCard
    }
};
</script>

<style scoped>
.carousel {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 100%;
}
/* .slide-enter-active, .slide-leave-active {
    transition: transform 0.2s ease-in-out;
}

.slide-enter-from{
    transform: translateX(400px);
}

.slide-enter-to {
    transform: translateX(0px);
}

.slide-leave-to {
    transform: translateX(-400px);
} */


</style>