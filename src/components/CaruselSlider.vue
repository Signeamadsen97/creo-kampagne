<script setup>
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";

const props = defineProps({
  slides: {
    type: Array,
    default: () => [],
  },
});

const breakpoints = {
  // 700px and up
  0: {
    itemsToShow: 1,
    snapAlign: "center",
  },

  700: {
    itemsToShow: 2,
    snapAlign: "center",
  },
};
</script>

<template>
  <div class="slider-box">
    <h1 class="h1_poppins">Det siger andre!</h1>
    <carousel :breakpoints="breakpoints">
      <slide v-for="slide in slides" :key="slide">
        <div class="slide">
          <img :src="slide.image.src" :alt="slide.image.alt" />
          <p class="body_poppins">{{ slide.text }}</p>
        </div>
      </slide>

      <template #addons>
        <navigation>
          <template #prev>
            <div class="slider_prev">
              <svg
                class="carousel__icon"
                viewBox="0 0 24 24"
                role="img"
                aria-label="Arrow pointing to the left"
              >
                <title>Arrow pointing to the left</title>
                <path
                  d="M15.41 16.59L10.83 12l4.58-4.59L14 6l-6 6 6 6 1.41-1.41z"
                ></path>
              </svg>
            </div>
          </template>
          <template #next>
            <div class="slider_prev">
              <svg
                class="carousel__icon"
                viewBox="0 0 24 24"
                role="img"
                aria-label="Arrow pointing to the right"
              >
                <title>Arrow pointing to the right</title>
                <path
                  d="M8.59 16.59L13.17 12 8.59 7.41 10 6l6 6-6 6-1.41-1.41z"
                ></path>
              </svg>
            </div>
          </template>
        </navigation>

        <pagination />
      </template>
    </carousel>
  </div>
</template>

<style scoped lang="scss">
.slider-box {
  --vc-nav-color: green;
  
  padding-top: 114px;
}
.slide {
  display: grid;
  gap: 10px;
  margin: 0 50px;

  img {
    width: 100%;
    aspect-ratio: 16/9;
  }
}
h1 {
  text-align: center;
  margin-bottom: 40px;
}

.body_poppins {
  font-weight: 600;
  font-size: 25px;
  text-align: center;
}
</style>
