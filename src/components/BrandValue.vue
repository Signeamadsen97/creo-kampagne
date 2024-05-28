<script setup></script>

<template>
  <div class="brand_wrapper">
    <h1 class="h1_poppins">Vi går op i</h1>
    <div class="grid">
      <div class="icon1">
        <img src="./icon/icon1.svg" alt="" />
        <h2 class="h2_poppins">Fedt nok</h2>
      </div>
      <div class="icon2">
        <img src="./icon/icon2.svg" alt="" />
        <h2 class="h2_poppins">Fedt nok</h2>
      </div>
      <div class="icon3">
        <img src="./icon/icon3.svg" alt="" />
        <h2 class="h2_poppins">Fedt nok</h2>
      </div>

      <div class="icon4">
        <img src="./icon/icon4.svg" alt="" />
        <h2 class="h2_poppins">Fedt nok</h2>
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 50px;

  @media screen and (max-width: 730px) {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}

.h1_poppins {
  text-align: center;
  font-size: 45px;
  color: black;
}

.h2_poppins {
  display: grid;
  text-align: center;
  color: black;
  font-weight: 400;
}

.grid img {
  width: 100%;
}

.brand_wrapper {
  padding: var(--wrapper-padding);
  background: linear-gradient(270deg, #d4d4aa, #fefae0, #616d38);
  background-size: 600% 600%;
  animation: gradientAnimation 10s ease infinite;
}

@keyframes gradientAnimation {
  0% {
    background-position: 0% 50%;
  }

  50% {
    background-position: 100% 50%;
  }

  100% {
    background-position: 0% 50%;
  }
}</style>
