<script setup>
import CreoIntro from "@/components/CreoIntro.vue";
import HvemErVi from "@/components/HvemErVi.vue";
import TextMedia from "@/components/TextMedia.vue";

const profiles = [
  {
    img: "https://fakeimg.pl/467x549",
    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Iure voluptates soluta ex temporibus officiis dicta sed saepe rerum. Eaque, quidem?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Iure voluptates soluta ex temporibus officiis dicta sed saepe rerum. Eaque, quidem?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Iure voluptates soluta ex temporibus officiis dicta sed saepe rerum. Eaque, quidem?",
  },
  {
    img: "https://fakeimg.pl/467x549",
    text: "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Iure voluptates soluta ex temporibus officiis dicta sed saepe rerum. Eaque, quidem?",
  },
];
</script>

<template>
  <div>
    <CreoIntro />

    <TextMedia
      :vertical="true"
      heading="Om os"
      grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
      grid-text="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      grid-image-src="https://fakeimg.pl/467x549"
    />

    <HvemErVi :profiles="profiles" />
  </div>
</template>

<style scoped></style>
