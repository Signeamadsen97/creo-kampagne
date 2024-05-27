<script setup></script>

<template>
  <div class="footer_wrapper">
    <div class="grid">
      <p class="text">
        Boulevarden bringer samfundet sammen og styrker tilliden gennem samarbejde.
      </p>
      <div class="list">
        <ul>
          <h3 class="h3_poppins">Forside</h3>
          <div class="body_poppins">
            <a href="#introduction_video"><li>Introduktion video</li></a>
            <a href="#about_project"><li>Om os</li></a>
            <a href="#interview_video"><li>Se hvad andre tænker</li></a>
            <a href="#poll_text"><li>Giv os din mening</li></a>
            <a href="#before_image"><li>Før og efter billeder</li></a>
          </div>
        </ul>

        <ul>
          <h3 class="h3_poppins">Om Creo</h3>
          <div class="body_poppins">
            <a href="aboutview.vue.html#who_we"><li>Hvem er vi</li></a>
            <a href="#why_do"><li>Hvorfor vil vi det her</li></a>
            <a href="#we_are"><li>Profiler fra Creo</li></a>
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

  @media screen and (max-width: 900px) {
    display: flex;
    flex-direction: column;
    grid-template-areas: none;
  }
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

  @media screen and (max-width: 750px) {
    justify-content: center;
    flex-direction: column;
    align-items: center;
    gap: 40px;
  }
}

.text {
  grid-area: text;
  color: #606c38;
  font-size: 55px;

  @media screen and (max-width: 900px) {
    margin-bottom: 70px;
    font-size: 30px;
  }
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
