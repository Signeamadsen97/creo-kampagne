<script setup></script>

<template>
  <h1 class="h2_poppins">Brand værdi</h1>
  <div class="brand_wrapper">
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

h1 {}

.brand_wrapper {
  background-color: #D4D4AA;
  padding: var(--wrapper-padding);

}
</style>
