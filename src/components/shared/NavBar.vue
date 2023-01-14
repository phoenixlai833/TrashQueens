<script setup>
import NavBarItem from './NavBarItem.vue';
</script>

<template>
    <nav class="navbar">
        <NavBarItem navIcon='icon-park-twotone:home' navName='Home' navTo='/' navColor='#F5F9E9' />
        <NavBarItem navIcon='icon-park-twotone:game-ps' navName='Game' navTo='/game' navColor='#F5F9E9' />
        <NavBarItem navIcon='icon-park-twotone:book-open' navName='Education' navTo='/education' navColor='#F5F9E9' />
        <NavBarItem navIcon='icon-park-twotone:every-user' navName='About Us' navTo='/about' navColor='#F5F9E9' />
    </nav>
</template>

<script>
export default {
    name: "NavBar",
    components: {
        NavBarItem
    }
};
</script>

<style scoped>
.navbar {
    display: flex;
    justify-content: space-evenly;
    position: fixed;
    width: 100%;
    background-color: #5AB4AB;
    padding: 1rem 0;
    bottom: 0;
}
</style>