<script setup></script>

<template>
  <div class="brand_wrapper">
    <h1>Brand værdi</h1>
    <div class="grid">
      <img src="https://fakeimg.pl/251x181" alt="" />
      <img src="https://fakeimg.pl/251x181" alt="" />
      <img src="https://fakeimg.pl/251x181" alt="" />
      <img src="https://fakeimg.pl/251x181" alt="" />
    </div>
  </div>
</template>

<style scoped>
.grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 50px;
    
}
.grid img {
    width: 100%;
}

h1 {
    text-align: center;
}

.brand_wrapper {
    background-color: green;
    padding: var(--wrapper-padding)
}

</style>
