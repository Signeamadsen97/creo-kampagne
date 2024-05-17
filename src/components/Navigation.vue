<script setup>

</script>


<template>
    <nav>
        <ul>
            <li>
                <RouterLink class="logo h2_poppins" to="/">Boulevarden</RouterLink>
            </li>
            <li>
                <RouterLink class="h3_poppins" to="/about">Om Creo</RouterLink>
            </li>
        </ul>
    </nav>
</template>


<style scoped>
nav {
    background-color: #FEFAE0;
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
    text-decoration: none;
    font-size: 30px;
}

.logo {
    font-size: 40px;
}
</style>