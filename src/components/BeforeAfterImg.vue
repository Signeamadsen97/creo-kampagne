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
});
</script>

<template>
  <div class="before_wrapper" :class="{ reverse: reverse }">
    <h1 class="before_header">Fremtiden på OUH</h1>
    <div class="grid">
      <div class="text">
        <div class="description_text"></div>
        <h2>Før og efter, hallo det er fedt?</h2>
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,
        </p>
      </div>
      <img
        src="https://fakeimg.pl/853x568"
        alt="beforeafterimg"
        class="before_img"
      />
      <h3 class="bigtext">Måske en fed ting eller 2?</h3>
    </div>
  </div>
</template>

<style scoped lang="scss">
.before_wrapper {
  background-color: green;
  padding: 50px var(--wrapper-padding-x);

  &.reverse {

    background-color: white;
    .grid {
      grid-template-areas:  ". text"
                            "bigtext image";
    }

    .before_header {
      display: none;
    }
  }
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  grid-template-rows: auto auto;
  grid-template-areas:  "text ."
                        "image bigtext";
  width: 100%;
}

.bigtext {
  display: grid;
  align-items: center;
  font-size: 96px;
  grid-area: bigtext;
}

.before_img {
  width: 100%;
  grid-area: image;
}

.text {
  grid-area: text;
}
</style>
