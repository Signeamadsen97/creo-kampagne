<script setup>
import Hero from "@/components/Hero.vue";
import BrandValue from "@/components/BrandValue.vue";
import TextMedia from "@/components/TextMedia.vue";
import PageBreaker from "@/components/PageBreaker.vue";
import TextBox from "@/components/TextBox.vue";
import PollBox from "@/components/PollBox.vue";
import CaruselSlider from "@/components/CaruselSlider.vue";

import BeforeAfterImg from '@/components/BeforeAfterImg.vue';

import beforeImage1 from '@/components/icon/before1.jpg';
import afterImage1 from '@/components/icon/after1.jpg';
import beforeImage2 from '@/components/icon/before2.jpg';
import afterImage2 from '@/components/icon/after2.jpg';

import { ref } from "vue";



const items = ref([
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 1",
    },
  },
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 2",
    },
  },
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 3",
    },
  },
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 4",
    },
  },
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 5",
    },
  },
  {
    text: "Lorem Ipsum is simply dummy text of the printing",
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 6",
    },
  },
]);
</script>

<template>
  <main>
    <div class="wrapper">
      <Hero />
    </div>
    <BrandValue />
    <div class="text-media-grid">
      <TextMedia heading="Om os" grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
        grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-image-src="https://fakeimg.pl/467x549" />
      <TextMedia heading="" grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
        grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-image-src="https://fakeimg.pl/467x549" :reverse="true" />
    </div>
    <PageBreaker />
    <TextMedia heading="" grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
      grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      grid-text-bottom="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      grid-image-src="https://fakeimg.pl/774x516" :vertical="true" />
    <div class="poll-grid">
      <TextBox />
      <PollBox />
    </div>

    <CaruselSlider :slides="items" />

    <BeforeAfterImg mainHeading="" subHeading="Før og efter, hallo det er fedt"
      bodyText="Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,"
      bigText="Måske en fed ting eller 2?" :beforeImage="beforeImage1" :afterImage="afterImage1" />

    <BeforeAfterImg :reverse="true" mainHeading="Reverseret Sektion" subHeading="Dette er en reverseret sektion"
      bodyText="Dette er noget anderledes tekst for den reverserede sektion." bigText="Nogle store ord her!"
      :beforeImage="beforeImage2" :afterImage="afterImage2" />
  </main>
</template>

<style scoped>
.text-media-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.poll-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
}
</style>
