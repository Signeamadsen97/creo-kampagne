<script setup></script>

<template>
  <div class="footer_wrapper">
    <div class="grid">
      <p>
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the.
      </p>

      <ul>
        <h3>Navigation</h3>
        <li>Navigation</li>
        <li>Navigation</li>
        <li>Navigation</li>
        <li>Navigation</li>
      </ul>

      <ul>
        <h3>Andet Info</h3>
        <li>Andet info</li>
        <li>Andet info</li>
        <li>Andet Info</li>
        <li>Andet Info</li>
      </ul>
    </div>
    <div class="some_img">
      <img src="https://fakeimg.pl/58x58" alt="FB">
      <img src="https://fakeimg.pl/58x58" alt="IG">
      <img src="https://fakeimg.pl/58x58" alt="LD">


    </div>
  </div>
</template>

<style scoped>

.footer_wrapper {
  background-color: lightgreen;
  padding: 50px var(--wrapper-padding-x);
}
.grid {
    display: grid;
    grid-template-columns: 1.5fr 1fr 1fr;
}
.some_img {
  
}
</style>
