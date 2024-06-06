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
  gridInterview: {
    type: String,
    default: "",
  },
  overflow: {
    // Ny prop til at bestemme om billedet skal overlappe
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <div class="media_wrapper" :class="{
    reverse: reverse,
    vertical: vertical,
    'hide-heading': hideHeading,
    'about-us': aboutUs,
    overflow: overflow,
  }">
    <h1 v-if="heading?.length" class="media_heading h2_poppins">
      {{ heading }}
    </h1>
    <div class="grid">
      <div class="media_text">
        <h2 v-if="gridHeading.length" class="h3_poppins">{{ gridHeading }}</h2>
        <p v-if="gridTextTop.length" class="body_poppins" v-html="gridTextTop"></p>
        <p v-if="gridTextBottom.length" class="body_poppins">
          {{ gridTextBottom }}
        </p>
      </div>
      <img v-if="gridImageSrc.length" :src="gridImageSrc" alt="" class="media_img" />
      <video v-if="gridInterview" class="interview_media" controls>
        <source :src="gridInterview" />
      </video>
    </div>
  </div>
</template>

<style scoped lang="scss">
.media_wrapper {
  padding: 30px var(--wrapper-padding-x);

  .h3_poppins {
    line-height: 3rem;
  }

  .body_poppins {
    line-height: 2.2rem;
  }

  &.reverse {
    .media_text {
      order: 2;

      .grid {
        grid-template-columns: 1fr 1.5fr;
      }

      @media screen and (max-width: 900px) {
        order: -1;
      }
      
      .h3_poppins {
        padding-top: 20px;
      }
    }

    .media_img {
      order: -1;
      @media screen and (max-width: 900px) {
         padding-bottom: 40px;
        }
    }
  }

  &.vertical {
    padding-left: 0px;
    padding-top: 120px;
    padding-bottom: 65px;

    @media screen and (max-width: 400px) {
          padding-left: 0px;
        }

    .grid {
      grid-template-columns: 1.3fr 1fr;
      gap: 104px;

      @media screen and (max-width: 900px) {
          gap: 10px;
        }
      

      .media_text {
        width: 70%;
        padding-bottom: 20%;
        order: 2;
        margin-left: 30px;

        @media screen and (max-width: 900px) {
          padding-bottom: 0px;
          width: 100%;
        }
        @media screen and (max-width: 400px) {
          padding-right: 0px;
          width: 100%;
        }
      }

      .interview_media {
        width: 100%;
        order: 1;
        margin-left: 65px;

        @media screen and (max-width: 900px) {
          display: flex;
          margin: 35px;
          padding: 0px;
          order: 2;
        }
        @media screen and (max-width: 400px) {
          display: flex;
          padding-right: 0px;
          justify-content: center;
          order: 2;
          margin: 35px;
        }

      }

      .h3_poppins {
        padding-bottom: 10%;
        line-height: 3rem;
        font-weight: 600;
        font-size: 2rem;
        @media screen and (max-width: 400px) {
          font-size: 20px;
        }
      }

      .body_poppins {
        line-height: 2rem;
        font-size: 1.5rem;
        @media screen and (max-width: 400px) {
          font-size: 15px;
        }
      }

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
