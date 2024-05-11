<script setup>

</script>


<template>
<nav>
    <ul>
        <li><RouterLink class="logo" to="/">Kampagne Navn</RouterLink></li>
        <li><RouterLink to="/about">Om Creo</RouterLink></li>
    </ul>
</nav>

</template>


<style scoped>
nav {
    background-color: green;
    padding: 10px 65px;
}

ul {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0;
    list-style: none;
}

li a {
    color: black;
    text-decoration: none;
    font-size: 30px;
}

.logo {
    font-size: 40px;
}

</style>