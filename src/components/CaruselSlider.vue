<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

const props = defineProps({
  slides: {
    type: Array,
    default: () => [],
  },
});
</script>

<template>
  <div class="slider-box">
    <carousel :items-to-show="3.5">
      <slide v-for="slide in slides" :key="slide">
        <div class="slide">
          <img :src="slide.image.src" :alt="slide.image.alt" />
          <p>{{ slide.text }}</p>
        </div>
      </slide>

      <template #addons>
        <navigation />
        <pagination />
      </template>
    </carousel>
  </div>
</template>

<style scoped lang="scss">
.slider-box {
  padding-top: 114px;
}
.slide {
  display: grid;
  gap: 10px;
  margin: 0 10px;

  img {
    width: 100%;
    aspect-ratio: 16/9;
  }
}
</style>
