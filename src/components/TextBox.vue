<script setup></script>

<template>
  <div class="grid">
    <div class="text">
    </div>

    <div class="textbox">
      <h2 class="h2_poppins">Hvofor din mening gir mening</h2>
      <p class="body_poppins">
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s, Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s,
      </p>
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
  color: black;
}


</style>
