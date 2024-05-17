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
  overflow: { // Ny prop til at bestemme om billedet skal overlappe
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
    'overflow': overflow,
  }">
    <h1 v-if="heading?.length" class="media_heading h2_poppins">
      {{ heading }}
    </h1>
    <div class="grid">
      <div class="media_text">
        <h2 class="h3_poppins">{{ gridHeading }}</h2>
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
    }

    .media_text {
      order: 2;
      padding-left: 104px;
    }

    .media_img {
      order: -1;
      margin-top: 50px;
    }
  }

  &.about-us {
    .media_img {
      width: 100%;
    }
  }

  &.overflow {
    .media_img {
      position: relative;
      z-index: 1;
      margin-bottom: -100px;
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
