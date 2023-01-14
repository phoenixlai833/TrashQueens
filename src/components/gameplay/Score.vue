
<template>
    <div>
        <div class="scoreContainer">
            <GoBack :isGame=true />
            <div>
                <span>Lives: {{ livesLeft }}</span>
                &nbsp;&nbsp;
                <span>Score: {{ currentScore }}</span>
            </div>
        </div>
    </div>
</template>

<script>
import GoBack from "../shared/GoBack.vue";
export default {
    props: [
        "currentScore",
        "livesLeft"
    ],
    components: { GoBack }
};
</script>

<style scoped>
.scoreContainer {
    width: 100vw;
    min-height: 5vh;
    background-color: #F5F9E9;
    border-radius: 0 0 10px 10px;
    box-shadow: 0 4px 4px 2px rgba(0, 0, 0, 0.25);
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 1% 3%;
    font-size: 1rem;
    font-family: "Nunito-Regular";
}
</style>