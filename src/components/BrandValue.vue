<script setup></script>

<template>
  <div class="brand_wrapper">
    <h1 class="h1_poppins">Vi går op i</h1>
    <div class="grid">
      <div class="icon1">
        <img src="./icon/icon1.svg" alt="" />
        <h2 class="h2_poppins">Inklusion</h2>
        <p class="body_poppins">Byens borgere skal have mulighed for at inkludere og engagere sig i byens udvikling</p>
      </div>
      <div class="icon2">
        <img src="./icon/icon2.svg" alt="" />
        <h2 class="h2_poppins">Professionel tillid</h2>
        <p class="body_poppins">Vi leverer professionelle løsninger, basert på jeres ønsker, i samarbejde med eksperter og
          fagfolk.</p>
      </div>
      <div class="icon3">
        <img src="./icon/icon3.svg" alt="" />
        <h2 class="h2_poppins">Mennesket i fokus</h2>
        <p class="body_poppins">Byens borgere skal have mulighed for at inkludere og engagere sig i byens udvikling</p>
      </div>

      <div class="icon4">
        <img src="./icon/icon4.svg" alt="" />
        <h2 class="h2_poppins">Historisk ansvar</h2>
        <p class="body_poppins">Vi bygger på arven fra tidligere bygningsprojekter og fortsætter med at skabe høj kvalitet
          og værdi</p>
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 70px;

  @media screen and (max-width: 900px) {
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
  color: black;
  font-weight: 400;
}

.grid img {
  width: 70%;
}

.brand_wrapper {
  padding: var(--wrapper-padding);
  margin-bottom: 5%;
  background: linear-gradient(270deg, #616d38, #d4d4aa, #fefae0);
  background-size: 600% 600%;
  animation: gradientAnimation 8s ease infinite;
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
}
</style>
