
<template>
    <div>
        <div class="finalScoreContainer">
            <img src="/assets/trees.png" alt="cartoon trees">
            <span>Your Score: {{ finalScore }}</span>
        </div>
    </div>
</template>

<script>
export default {
    props: [
        "finalScore"
    ]
};
</script>

<style scoped>
.finalScoreContainer {
    width: 60vw;
    display: flex;
    flex-direction: column;
    align-items: center;
}

span {
    font-size: 2rem;
    font-weight: 800;
    font-family: "Nunito-Bold", sans-serif;
    margin: 30px 0;
}
</style>