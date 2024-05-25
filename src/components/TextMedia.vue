<script setup>
const props = defineProps({
  heading: {
    type: String,
    default: "",
  },
  gridHeading: {
    type: String,
    default: "",
  },
  gridTextTop: {
    type: String,
    default: "",
  },
  gridTextBottom: {
    type: String,
    default: "",
  },
  gridImageSrc: {
    type: String,
    default: "",
  },
  reverse: {
    type: Boolean,
    default: false,
  },
  vertical: {
    type: Boolean,
    default: false,
  },
  hideHeading: {
    type: Boolean,
    default: false,
  },
  aboutUs: {
    type: Boolean,
    default: false,
  },
  overflow: {
    // Ny prop til at bestemme om billedet skal overlappe
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <div
    class="media_wrapper"
    :class="{
      reverse: reverse,
      vertical: vertical,
      'hide-heading': hideHeading,
      'about-us': aboutUs,
      overflow: overflow,
    }"
  >
    <h1 v-if="heading?.length" class="media_heading h2_poppins">
      {{ heading }}
    </h1>
    <div class="grid">
      <div class="media_text">
        <h2 v-if="gridHeading.length" class="h3_poppins">{{ gridHeading }}</h2>
        <p v-if="gridTextTop.length" class="body_poppins">{{ gridTextTop }}</p>
        <p v-if="gridTextBottom.length" class="body_poppins">
          {{ gridTextBottom }}
        </p>
      </div>
      <img :src="gridImageSrc" alt="" class="media_img" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.media_wrapper {
  padding: 30px var(--wrapper-padding-x);

  &.reverse {
    .media_text {
      order: 2;
      @media screen and (max-width: 900px) {
        order: -1;
      }
    }

    .media_img {
      order: -1;
    }
  }

  &.vertical {
    padding-left: 0px;
    padding-top: 120px;

    .grid {
      grid-template-columns: 1fr 1fr;
      gap: 104px;

      @media screen and (max-width: 900px) {
        grid-template-columns: 1fr;
      }
    }

    .media_text {
      order: 2;
    }

    .media_img {
      order: -1;
      margin-top: 50px;
    }
  }

  &.about-us {
    @media screen and (max-width: 1000px) {
      padding: 0;
    }
    .media_img {
      width: 100%;
      height: 100%;
      margin-top: 0;
      translate: 0 50px;
      object-fit: cover;
    }

    .media_text {
      .body_poppins {
        margin-top: 50px;
        font-size: 30px;
      }
      @media screen and (max-width: 1000px) {
        padding: 30px var(--wrapper-padding-x);
      }
    }
    .grid {
      @media screen and (max-width: 1000px) {
        grid-template-columns: 1fr;
        gap: 30px;

        .media_img {
          width: 100%;
        }
      }
    }
  }

  &.overflow {
    .media_img {
      z-index: 1;
      position: relative;
      /* Tilføjet */
      margin-bottom: -90px;
      /* Juster margenen efter behov */
    }
  }
}

.grid {
  display: grid;
  grid-template-columns: 1fr;
  width: 100%;
}

.media_text {
  order: 1;
}

.media_img {
  width: 100%;
  order: 2;
}
</style>
