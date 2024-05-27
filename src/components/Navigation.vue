<script setup></script>

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
  background-color: #fefae0;
  padding: 10px 65px;
  @media screen and (max-width: 520px) {
    padding: 4px 20px;
  }
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

  @media screen and (max-width: 520px) {
    font-size: 20px;
  }
}

.logo {
  font-size: 40px;

  @media screen and (max-width: 900px) {
    font-size: 25px;
  }
}
</style>
