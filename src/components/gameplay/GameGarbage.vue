<template>
    <div class="garbage__container">
        <img :src=garbageUrl alt="trash" draggable="true">
        <!-- <img :src=> -->
        <span class="garbage__name">{{ selectedGarbage.garbageName }}</span>
    </div>
</template>

<script>
export default {
    name: "GameGarbage",
    methods: {
        getRandomGarbage() {
            this.selectedGarbage = this.garbages[Math.floor(Math.random() * this.garbages.length)]
            // this.garbageUrl = new URL(`/assets/garbages/trash-${this.selectedGarbage.garbageName}.svg`, import.meta.url)
            this.garbageUrl = `/assets/garbages/trash-${this.selectedGarbage.garbageName}.svg`
            // this.garbageUrl = this.selectedGarbage.garbageUrl
            this.setCurrentGarbage(this.selectedGarbage)
        }
    },
    computed: {

    },
    props: {
        setCurrentGarbage: Function
    },
    beforeMount() {
        this.getRandomGarbage()
    },
    data() {
        return {
            selectedGarbage: {},
            garbageUrl: '',
            garbages: [
                {
                    garbageName: 'apple',
                    garbageCategory: 'organics',
                    // garbageUrl: '/assets/garbages/trash-apple.svg'
                },
                {
                    garbageName: 'apple-bitten',
                    garbageCategory: 'organics',
                    // garbageUrl: '/assets/garbages/trash-apple-bitten.svg'
                },
                {
                    garbageName: 'avocado',
                    garbageCategory: 'organics',
                    // garbageUrl: '/assets/garbages/trash-avocado.svg'
                },
                {
                    garbageName: 'pizza',
                    garbageCategory: 'organicx',
                    // garbageUrl: '/assets/garbages/trash-pizza.svg'
                },
                {
                    garbageName: 'broken-glass',
                    garbageCategory: 'glass',
                    // garbageUrl: '/assets/garbages/trash-broken-glass.svg'
                },
                {
                    garbageName: 'broken-bottle',
                    garbageCategory: 'glass',
                    // garbageUrl: '/assets/garbages/trash-broken--bottle.svg'
                },
                {
                    garbageName: 'glass',
                    garbageCategory: 'glass',
                    // garbageUrl: '/assets/garbages/trash-broken--bottle.svg'
                },
                {
                    garbageName: 'can',
                    garbageCategory: 'metal',
                    // garbageUrl: '/assets/garbages/trash-can.svg'
                },
                {
                    garbageName: 'fork',
                    garbageCategory: 'metal',
                    // garbageUrl: '/assets/garbages/trash-fork.svg'
                },
                {
                    garbageName: 'frying-pan',
                    garbageCategory: 'metal',
                    // garbageUrl: '/assets/garbages/trash-frying-pan.svg'
                },
                {
                    garbageName: 'cardbox',
                    garbageCategory: 'paper',
                    // garbageUrl: '/assets/garbages/trash-cardbox.svg'
                },
                {
                    garbageName: 'airplane',
                    garbageCategory: 'paper',
                    // garbageUrl: '/assets/garbages/trash-airplane.svg'
                },
                {
                    garbageName: 'newspaper',
                    garbageCategory: 'paper',
                    // garbageUrl: '/assets/garbages/trash-newspaper.svg'
                },
                {
                    garbageName: 'mouse',
                    garbageCategory: 'e-waste',
                    // garbageUrl: '/assets/garbages/trash-mouse.svg'
                },
                {
                    garbageName: 'hairdryer',
                    garbageCategory: 'e-waste',
                    // garbageUrl: '/assets/garbages/trash-hairdyer.svg'

                },
                {
                    garbageName: 'computer',
                    garbageCategory: 'e-waste',
                    // garbageUrl: '/assets/garbages/trash-computer.svg'
                },
                {
                    garbageName: 'bag',
                    garbageCategory: 'plastic',
                    // garbageUrl: '/assets/garbages/trash-plastic-bag.svg'
                },
                {
                    garbageName: 'bottle',
                    garbageCategory: 'plastic',
                    // garbageUrl: '/assets/garbages/trash-plastic-bottle.svg'

                },
                {
                    garbageName: 'cup',
                    garbageCategory: 'plastic',
                    // garbageUrl: '/assets/garbages/trash-plastic-cup.svg'

                },
            ]
        };
    }
}
</script>

<style scoped>
.garbage__container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    /* width: 9.063rem; */
    height: 3.979rem;
}

img {
    width: 100%;
    height: 100%;
    margin-bottom: 1rem;
    z-index: 1;
    filter: drop-shadow(3px 5px 2px rgb(0 0 0 / 0.4));
}

span {
    display: flex;
    align-items: center;
    border-radius: 0.625rem;
    background-color: #fff5e9;
    color: black;
    padding: 1rem;
    height: 1.223rem;
    font-family: "FuzzyBubbles-Regular", sans-serif;
    font-size: 1.063rem;
    font-weight: bold;
}
</style>