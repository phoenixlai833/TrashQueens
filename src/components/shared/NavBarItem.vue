<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Iconify from './Iconify.vue';

</script>

<template>
    <div class="navbar-item">
        <RouterLink :to=navTo class="navbar-link">
            <Iconify :iconName=navIcon :iconColor=navColor :iconHeight=40 />
            {{ navName }}
        </RouterLink>
    </div>
</template>

<script>
export default {
    name: "NavBar",
    props: {
        navName: {
            type: String,
            required: true
        },
        navTo: {
            type: String,
            required: true
        },
        navIcon: {
            type: String,
            required: true
        },
        navColor: {
            type: String,
            required: true
        }
    },
    components: {
        Iconify
    },
    data() {
        return {};
    },
};
</script>

<style scoped>
/* .navbar-item {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
    } */
.navbar-link {
    color: #F5F9E9;
    font-size: 0.75rem;
    font-family: "Nunito-Regular";
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
}
</style>