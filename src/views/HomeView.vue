<script setup>
import Hero from "@/components/Hero.vue";
import BrandValue from "@/components/BrandValue.vue";
import TextMedia from "@/components/TextMedia.vue";
import PageBreaker from "@/components/PageBreaker.vue";
import TextBox from "@/components/TextBox.vue";
import PollBox from "@/components/PollBox.vue";
import CaruselSlider from "@/components/CaruselSlider.vue";

import { ref } from "vue";
import BeforeAfterImg from "@/components/BeforeAfterImg.vue";

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
    <div class="wrapper"><Hero /></div>
    <BrandValue />
    <div class="text-media-grid">
      <TextMedia
        heading="Om os"
        grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
        grid-text="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-image-src="https://fakeimg.pl/467x549"
      />
      <TextMedia
        heading="Om os"
        grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
        grid-text="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-image-src="https://fakeimg.pl/467x549"
        :reverse="true"
      />
    </div>
    <PageBreaker />
    <TextMedia
      heading="Om os"
      grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
      grid-text="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
      grid-image-src="https://fakeimg.pl/467x549"
      :vertical="true"
    />
    <div class="poll-grid">
      <TextBox />
      <PollBox />
    </div>

    <CaruselSlider :slides="items" />
    <BeforeAfterImg />
    <BeforeAfterImg :reverse="true" />
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
