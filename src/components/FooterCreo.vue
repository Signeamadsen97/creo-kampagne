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
          <h3 class="h3_poppins">Navigation</h3>
          <div class="body_poppins">
            <a href=""><li>Navigation</li></a>
            <a href=""><li>Navigation</li></a>
            <a href=""><li>Navigation</li></a>
            <a href=""><li>Navigation</li></a>
          </div>
        </ul>

        <ul>
          <h3 class="h3_poppins">Andet Info</h3>
          <div class="body_poppins">
            <a href=""><li>Andet info</li></a>
            <a href=""><li>Andet info</li></a>
            <a href=""><li>Andet info</li></a>
            <a href=""><li>Andet info</li></a>
          </div>
        </ul>
      </div>

      <div class="some_img">
        <a href=""><img src="./icon/somelogo.png" alt="LD" /></a>
        <a href=""><img src="./icon/iglogo.png" alt="IG" /></a>
        <a href=""><img src="./icon/fblogo.png" alt="FB" /></a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer_wrapper {
  background-color: #fefae0;
  padding: 50px var(--wrapper-padding-x);
}

.grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  grid-template-rows: auto auto;
  grid-template-areas:
    "text list"
    ". some";
}

.some_img {
  display: flex;
  gap: 40px;
  grid-area: some;
  padding-top: 40px;
  justify-content: end;
}

a:hover img {
  filter: brightness(0);
}

.list {
  grid-area: list;
  display: flex;
  gap: 150px;
  justify-content: center;

  h3 {
    padding-bottom: 40px;
  }
}

.text {
  grid-area: text;
  color: #606c38;
  font-size: 45px;
}

li {
  display: flex;
  margin-bottom: 25px;
  font-size: 19px;
}

a {
  text-decoration: none;
  color: #606c38;
}

a:hover {
  color: black;
  font-weight: 800;
}
</style>
