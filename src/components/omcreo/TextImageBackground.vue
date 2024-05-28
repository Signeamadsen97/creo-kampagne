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
        <img class="img_tib" src="https://fakeimg.pl/467x549" alt="" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 1.3fr;
}

.h1_poppins {
  padding-bottom: 30px;
}

.header1 {
  margin-left: 20%
}

.header2 {
  margin-left: 40%
}

.h3_poppins {
  width: 500px;
  color: black;
  margin-left: 10%;
  line-height: 3rem;
}

.wrapper {
  background-color: #FEFAE0;
  display: grid;
}

.img_tib {
  width: 100%;
}
</style>
