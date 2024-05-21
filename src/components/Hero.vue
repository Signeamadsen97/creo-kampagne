<script setup></script>

<template>
  <div class="grid">
    <div>
      <p class="header_text body_poppins">
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s,
      </p>
    </div>

    <div>
      <h1 class="hero_1 h1_poppins">Boulevarden Odense</h1>
      <img class="heromedia" src="https://fakeimg.pl/982x589" alt="" />
      <h1 class="hero_2 h1_poppins ">Dit nye område midt i byen</h1>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 19.95841995841996dvw 68.05266805266805dvw;
  gap: 3.049203049203049dvw;
}



.heromedia {
  width: 100%;
  z-index: 0;
}

.hero-container {
  display: flex;
  flex-direction: column;
  position: relative;
}

.header_text {
  padding-top: 10rem;
}

.hero_1 {
  margin-left: -3rem;
  margin-bottom: -25px;
  z-index: 1;
}

.hero_2 {
  position: absolute;
  right: 0;
  margin-right: 1rem;
  margin-top: -75px;
}

.grid {
  padding-bottom: 8rem;
}
</style>
