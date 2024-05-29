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
    img: simonImage,
    text: "Creo har historisk tilknytning til området, vi vil gerne være en del af dens fremtid",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Området har potentiale til fanstiske grønne områder",
  },
  {
    img: kristinaImage,
    text: "Man kan virkelig slippe drømmene løs og tænke stort",
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
      grid-text-top="Som arkitekter er vores største opgave at skabe rammerne, som vores liv og drømme udfolder sig i. <br/> <br/>
      Vores fokus er på bæredygtighed og genavendelse hvor det er muligt. Vores bygninger skal fremme livet, derfor lytter vi og er nysgerrige"
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
