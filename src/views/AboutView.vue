<script setup>
import CreoIntro from "@/components/omcreo/CreoIntro.vue";
import HvemErVi from "@/components/omcreo/HvemErVi.vue";
import TextImageBackground from "@/components/omcreo/TextImageBackground.vue";
import TextMedia from "@/components/TextMedia.vue";

const profiles = [
  {
    img: "https://fakeimg.pl/467x549",
    text: "Jeg er vild med at lege med bygninger?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Jeg er vild med at lege med bygninger?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Jeg er vild med at lege med bygninger?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Jeg er vild med at lege med bygninger?",
  },
];
</script>

<template>
  <div>
    <CreoIntro />

    <TextMedia
      :about-us="true"
      :vertical="true"
      grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      grid-image-src="https://fakeimg.pl/696x496"
    />

    <TextImageBackground />

    <HvemErVi :profiles="profiles" />
  </div>
</template>

<style scoped></style>
