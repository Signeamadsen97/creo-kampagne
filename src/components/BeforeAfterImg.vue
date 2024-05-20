<script setup>
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
    default: "Fremtiden på OUH",
  },
  subHeading: {
    type: String,
    default: "Før og efter, hallo det er fedt",
  },
  bodyText: {
    type: String,
    default: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s,",
  },
  bigText: {
    type: String,
    default: "Måske en fed ting eller 2?",
  },
  imageSrc: {
    type: String,
    default: "https://fakeimg.pl/853x568",
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
      <img :src="imageSrc" alt="beforeafterimg" class="image" />
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
  /* Center indholdet horisontalt */
  align-items: center;
  /* Center indholdet vertikalt */
  text-align: center;
  /* Centrer teksten */
}


.before_img {
  width: 100%;
  grid-area: image;
}

.text {
  grid-area: text;
}
</style>
