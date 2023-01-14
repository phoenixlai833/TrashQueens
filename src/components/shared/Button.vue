<template>
    <button class="game-button" :class="variant">
        {{ text }}
    </button>
</template>

<script>
export default {
    name: "Button",
    methods: {},
    computed: {},
    props: {
        text: {
            type: String,
            required: true
        },
        variant: {
            type: String,
            default: "primary",
            required: true
        }
    },
    data() {
        return {};
    },
};
</script>

<style scoped>
.game-button {
    border: none;
    color: #F5F9E9;
    border-radius: 8px;
    cursor: pointer;
    display: inline-block;
    font-size: 1.5rem;
    font-family: "Nunito-Bold", sans-serif;
    margin: 0;
    padding: 1rem 2rem;
    text-align: center;
    transition: all 0.2s;
}

.game-button:hover {
    transform: translateY(-0.2rem);
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.35));
}

.game-button:active {
    transform: translateY(0.1rem);
    filter: none;
}

.primary {
    background-color: #273D4E;
    color: #F5F9E9;
}

.primary:hover {
    background-color: #F5F9E9;
    color:#273D4E;
}

.primary:active {
    background-color: #5AB4AB;
    color: #F5F9E9;
}

.game {
    background-color: #273D4E;
    color: #F5F9E9;
}

.game:hover {
    background-color: #5AB4AB;
    color: #F5F9E9;
}

.game:active {
    background-color: #8C8C8C;
    color: #F5F9E9;
    filter: none;
}

.alternate {
    background-color: #5AB4AB;
    color: #F5F9E9;
}

.alternate:hover {
    background-color: #273D4E;
    color: #F5F9E9;
}

.alternate:active {
    background-color: #8C8C8C;
    color: #F5F9E9;
    filter: none;
}

.tutorial {
    font-family: "Nunito-Regular", sans-serif;
    font-size: 1rem;
    padding: 0.5rem 0;
    background-color: #F7C932;
    color: #273D4E;
    border-radius: 4px;
    width: 9.5rem;
}

.tutorial:hover {
    background-color: #F5F9E9;
    color: #273D4E;
}

.tutorial:active {
    background-color: #8C8C8C;
    color: #F5F9E9;
    filter: none;
}

.tutorial-alternate {
    font-size: 0.875rem;
    padding: 0.5rem 1rem;
    background-color: #273D4E;
    color: #F5F9E9;
    filter: drop-shadow(0px 4px 4px rgba(0, 0, 0, 0.45));
    border-radius: 4px;
}

.tutorial-alternate:hover {
    background-color: #F7C932;
    color: #273D4E;
}

.tutorial-alternate:active {
    background-color: #5AB4AB;
    color: #F5F9E9;
}

.education {
    font-size: 1rem;
    padding: 0.5rem 1rem;
    background-color: #273D4E;
    color: #F5F9E9;
}

.education:hover {
    background-color: #F5F9E9;
    color: #273D4E;
}

.education:active {
    background-color: #5AB4AB;
    color: #F5F9E9;
}

</style>