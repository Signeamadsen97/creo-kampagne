<script setup></script>

<template>
  <div class="grid">
    <div>
      <p class="body_poppins">
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
  padding-bottom: 8rem;
  margin-top: 50px;

  @media screen and (max-width: 850px) {
    display: flex;
    flex-direction: column-reverse;
  }

}



.heromedia {
  width: 100%;
  z-index: 0;
}

.body_poppins {
  padding-top: 10rem;
  font-weight: 400;
  font-size: 25px;
  color: black;

  @media screen and (max-width: 850px) {
    display: grid;
    grid-template-columns: 1fr;
    padding-top: 0;
    order: 2;
  }
}

.hero_1 {
  position: absolute;
  margin-left: -3rem;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
  @media screen and (max-width: 1200px) {
    display: grid;
    transform: none;
    left: auto;
    text-align: start;
    font-size: 25px;
  }
}

.hero_2 {
  position: absolute;
  right: 0;
  margin-right: 1rem;
  margin-top: -49px;

  @media screen and (max-width: 1200px) {
    display: grid;
    transform: none;
    left: auto;
    text-align: start;
    font-size: 25px;
    margin-top: -39px;
  }
}


</style>
