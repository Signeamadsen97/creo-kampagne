<script setup></script>

<template>
  <div class="media_wrapper">
    <h1>Om projekt</h1>
    <div class="grid">
      <h2>Køb 2 elefanter for 1</h2>
      <p>
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s,
      </p>
      <img src="https://fakeimg.pl/467x549" alt="">
    </div>
  </div>
</template>

<style scoped>
.media_wrapper {
    padding: var(--wrapper-padding)
}

.grid {
    display: grid;
    grid-template-columns: 1fr;
    width: 40%;
}

</style>
