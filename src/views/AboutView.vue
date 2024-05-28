<script setup>
import CreoIntro from "@/components/omcreo/CreoIntro.vue";
import HvemErVi from "@/components/omcreo/HvemErVi.vue";
import TextImageBackground from "@/components/omcreo/TextImageBackground.vue";
import TextMedia from "@/components/TextMedia.vue";

import kristinaImage from "@/components/icon/kristina.png";
import simonImage from "@/components/icon/simon.png";
import overblikImage from "@/components/icon/overblik.jpg"

const profiles = [
  {
    img: "https://fakeimg.pl/467x549",
    text: "Området har potentiale til fanstiske grønne områder",
  },
  {
    img: kristinaImage,
    text: "Man kan virkelig slippe drømmene løs og tænke stort",
  },
  {
    img: simonImage,
    text: "Creo har historisk tilknytning til området, vi vil gerne være med i dens fremtid",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Jeg er vild med at lege med bygninger?",
  },
];
</script>

<template>
  <div>
    <section id="who_we">
      <CreoIntro />
    </section>
    <TextMedia :about-us="true" :vertical="true"
      grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      :grid-image-src="overblikImage" />
    <section id="why_do">
      <TextImageBackground />
    </section>
    <section id="we_are">
      <HvemErVi :profiles="profiles" />
    </section>
  </div>
</template>

<style scoped></style>
