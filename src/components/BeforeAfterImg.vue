<script setup>
import BeforeAfterSlider from './BeforeAfterSlider.vue';

const props = defineProps({
  reverse: {
    type: Boolean,
    default: false,
  },
  vertical: {
    type: Boolean,
    default: false,
  },
  mainHeading: {
    type: String,
    default: "",
  },
  subHeading: {
    type: String,
    default: "",
  },
  bodyText: {
    type: String,
    default: "",
  },
  bigText: {
    type: String,
    default: "",
  },
  beforeImage: {
    type: String,
    required: true,
  },
  afterImage: {
    type: String,
    required: true,
  },
});
</script>

<template>
  <div class="wrapper" :class="{ reverse: reverse }">
    <h1 v-if="!reverse" class="header">{{ mainHeading }}</h1>
    <div class="grid">
      <div class="text">
        <div class="description_text"></div>
        <h2 class="h2_poppins">{{ subHeading }}</h2>
        <p class="body_poppins">{{ bodyText }}</p>
      </div>
      <div>
        <!-- Brug BeforeAfterSlider komponenten med props til billeder -->
        <BeforeAfterSlider :beforeImage="beforeImage" :afterImage="afterImage" />
      </div>
      <h3 class="bigtext h1_poppins">{{ bigText }}</h3>
    </div>
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  background-color: #D4D4AA;
  padding: 50px var(--wrapper-padding-x);
  margin-top: 80px;

  &.reverse {
    margin-top: -5px;
    background-color: white;

    .grid {
      grid-template-areas:
        "bigtext text"
        "bigtext image";
    }
  }
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  grid-template-areas:
    "text bigtext"
    "image bigtext";
  width: 100%;
  column-gap: 20px;
}

.bigtext {
  align-items: center;
  font-size: 96px;
  grid-area: bigtext;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.before_img {
  width: 100%;
  grid-area: image;
}

.text {
  grid-area: text;
}
</style>
