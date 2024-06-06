<script setup></script>

<template>
  <div class="creo_wrapper">
    <div class="logo">
      <img src="../icon/Logo.png" alt="" style="max-width: 100%; height: auto;" />
    </div>

    <h3 class="intro_text h2_poppins">
      Vi vil skabe arkitektur, de næste generationer ønsker at bevare.
    </h3>
  </div>
</template>

<style scoped>
.creo_wrapper {
  padding-left: 40px;
}

.logo {
  padding-top: 105px;
  padding-bottom: 40px;
}

.intro_text {
  padding-top: 80px;
  padding-left: 100px;
  font-size: 40px;
}
@media screen and (max-width: 700px) {
        .logo {
          padding-bottom: 0px;
          margin: 5px;
        }
        .intro_text {
          padding-left: 0px;
          font-size: 25px;
        }
      }

</style>
