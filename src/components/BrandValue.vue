<script setup></script>

<template>
  <h1 class="h2_poppins">Vi tror på</h1>
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

.h2_poppins {
  margin-left: 65px;
}

.brand_wrapper {
  padding: var(--wrapper-padding);
  background: linear-gradient(270deg, #D4D4AA, #FEFAE0, #616D38);
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
}
</style>