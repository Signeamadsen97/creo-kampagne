<script setup>
import BeforeAfterSlider from "./BeforeAfterSlider.vue";

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
  feedback: {
    type: Boolean,
    default: false,
  },
});

// Metoder til håndtering af klik-begivenheder
const handleLikeClick = () => {
  alert("Du har trykket på Like knappen!");
};

const handleDislikeClick = () => {
  alert("Du har trykket på Dislike knappen!");
};
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
      <div class="feedback-section">
        <button class="feedback-button like-button">
          <img src="./icon/like.png" alt="Like" class="feedback-image" @click="handleLikeClick">
        </button>
        <button class="feedback-button dislike-button">
          <img src="./icon/dislike.png" alt="Dislike" class="feedback-image" @click="handleDislikeClick">
        </button>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.wrapper {
  background-color: white;
  padding: 50px var(--wrapper-padding-x);
  margin-top: 80px;

  &.reverse {
    margin-top: -5px;
    background-color: #d4d4aa;

    .grid {
      grid-template-areas:
        "bigtext text"
        "bigtext image"
        "bigtext feedback";
    }
  }
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto auto;
  grid-template-areas:
    "text bigtext"
    "image bigtext"
    "feedback feedback";
  width: 100%;
  column-gap: 20px;

  @media screen and (max-width: 900px) {
    display: flex;
    flex-direction: column;
  }
}

.bigtext {
  align-items: center;
  font-size: 96px;
  grid-area: bigtext;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

  @media screen and (max-width: 900px) {
    font-size: 60px;
  }
}

.feedback-section {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
  gap: 10px;
}

.feedback-button {
  border: none;
  padding: 10px 20px;
  cursor: pointer;
  background: none;

  &:hover {
    filter: brightness(2.2);
    /* Lysere knap ved hover */
  }
}

.feedback-image {
  width: 50px;
  /* Juster størrelsen efter behov */
  height: auto;
}

.before_img {
  width: 100%;
  grid-area: image;
}

.text {
  grid-area: text;
}
</style>
