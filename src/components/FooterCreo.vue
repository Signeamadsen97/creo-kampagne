<script setup></script>

<template>
  <div class="footer_wrapper">
    <div class="grid">
      <p class="text">
        Boulevarden bringer samfundet sammen og styrker tilliden gennem
        samarbejde.
      </p>
      <div class="list">
        <ul>
          <RouterLink to="/"><h3 class="h3_poppins">Forside</h3></RouterLink>
          <div class="body_poppins">
            <li>
              <RouterLink
                class="footer-link"
                :to="{
                  path: '/',
                  query: { scrollTo: 'introduction_video' },
                }"
              >
                Om os
              </RouterLink>
            </li>

            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: '/', query: { scrollTo: 'about_project' } }"
              >
                Om projektet
              </RouterLink>
            </li>

            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: '/', query: { scrollTo: 'interview_video' } }"
              >
                Hør hvad andre tænker
              </RouterLink>
            </li>

            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: '/', query: { scrollTo: 'poll_text' } }"
              >
                Giv os din mening
              </RouterLink>
            </li>
            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: '/', query: { scrollTo: 'before_image' } }"
              >
                Før og efter billeder
              </RouterLink>
            </li>
          </div>
        </ul>

        <ul>
          <RouterLink to="/about"><h3 class="h3_poppins">Om Creo</h3></RouterLink>
          <div class="body_poppins">
            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: 'about', query: { scrollTo: 'who_we' } }"
              >
                Om os
              </RouterLink>
            </li>

            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: 'about', query: { scrollTo: 'why_do' } }"
              >
                Hvorfor vil vi det gerne
              </RouterLink>
            </li>

            <li>
              <RouterLink
                class="footer-link"
                :to="{ path: 'about', query: { scrollTo: 'we_are' } }"
              >
                Mere om os
              </RouterLink>
            </li>
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
  margin-bottom: 25px;
  font-size: 19px;
}

a {
  text-decoration: none;
}

.footer-link {
  color: #606c38;
}

a:hover {
  color: black;
  font-weight: 400;
}

ul {
  list-style-type: none;
}
</style>
