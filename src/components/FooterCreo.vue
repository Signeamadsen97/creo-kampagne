<script setup></script>

<template>
  <div class="footer_wrapper">
    <div class="grid">
      <p class="text">
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the.
      </p>
      <div class="list">
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
        <img src="https://fakeimg.pl/58x58" alt="FB" />
        <img src="https://fakeimg.pl/58x58" alt="IG" />
        <img src="https://fakeimg.pl/58x58" alt="LD" />
      </div>
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
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  grid-template-areas:
    "text list"
    ". some";
}
.some_img {
  display: flex;
  gap: 25px;
  grid-area: some;
  padding-top: 40px;
}

.list {
  grid-area: list;
  display: flex;
  gap: 150px;

  h3 {
    padding-bottom: 20px;
  }
}

.text {
  grid-area: text;
}


</style>
