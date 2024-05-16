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
  gridText: {
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
});
</script>

<template>
  <div class="media_wrapper" :class="{
    reverse: reverse,
    vertical: vertical,
    'hide-heading': hideHeading,
    'about-us': aboutUs,
  }">
    <h1 v-if="heading?.length" class="media_heading h2_poppins">{{ heading }}</h1>
    <div class="grid">
      <div class="media_text">
        <h2 class="h3_poppins">{{ gridHeading }}</h2>
        <p class="body_poppins">{{ gridText }}</p>
      </div>
      <img :src="gridImageSrc" alt="" class="media_img" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.media_wrapper {
  padding: 50px var(--wrapper-padding-x);

  &.reverse {
    .media_text {
      order: 2;
    }

    .media_img {
      order: -1;
    }
  }

  &.vertical {
    .grid {
      grid-template-columns: 1fr 1fr;
    }

    .media_text {
      order: 2;
    }

    .media_img {
      order: -1;
    }
  }

  &.about-us {
    .media_img {
      width: 100%;
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
