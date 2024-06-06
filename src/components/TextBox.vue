<script setup></script>

<template>
  <div class="grid">
    <div class="text">
    </div>

    <div class="textbox">
      <h2 class="h2_poppins">Odenses nye byområde - Boulevardens bliver bygget til dig.</h2>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr;

}

.textbox {
  background-color: #D4D4AA;
  padding: 50px var(--wrapper-padding-x);
}

.h2_poppins {
  width: 100%;
  max-width: 400px;
}

@media screen and (max-width: 450px) {
  .textbox {
    padding: 20px var(--wrapper-padding-x); /* Juster padding for mindre skærme */
  }

  .h2_poppins {
    width: 100%;
    max-width: 100%;
  }
}
</style>
