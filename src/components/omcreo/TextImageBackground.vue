<script setup></script>

<template>
  <div class="wrapper">
    <div>
      <h2 class="h1_poppins header1">Bag projektet</h2>
      <h2 class="h1_poppins header2">Creo Arkitekter</h2>
    </div>
    <div class="grid">
      <div class="text">
        <p class="h3_poppins">
          Creo har en helt særlig relation til Odense Universitetshospital. <br> <br>
          Den 13 etagers sengebygning, er nemlig opført i samarbejde med Jørgen Stærmose. <br> <br>
          Han er også manden bag Creo Arkitekter, da han i sin tid grundlagde tegnestuen. <br> <br>
          Creo Arkitekters relation til OUH og erfaring indenfor sundhedssektoren gør dem perfekte til dette projekt.
        </p>
      </div>
      <div class="img">
        <img class="img_tib" src="../icon/creostart.png" alt="" />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.grid {
  display: grid;
  grid-template-columns: 1fr 1.2fr;
  gap: 10px;
  place-items: center;
}

@media screen and (max-width: 850px) {
    .grid {
      display: grid;
      grid-template-columns: 1fr;
      grid-template-rows: 1fr;
    } 
  }


.h1_poppins {
  padding-bottom: 30px;
}

.header1 {
  padding-top: 20px;
  margin-left: 20%;
}

.header2 {
  margin-left: 40%
}

.h3_poppins {
  width: 500px;
  color: black;
}

.img_tib {
width: 100%;
max-height: 650px;
object-fit: cover;
}

.wrapper {
  display: grid;
  background: linear-gradient(270deg, #d4d4aa, #fefae0);
}
</style>
