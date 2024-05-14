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
    <div class="description_text">
      <h2>Før og efter, hallo det er fedt?</h2>
      <p>
        Lorem Ipsum is simply dummy text of the printing and typesetting
        industry. Lorem Ipsum has been the industry's standard dummy text ever
        since the 1500s,
      </p>
    </div>
    <div class="grid">
      <img
        src="https://fakeimg.pl/853x568"
        alt="beforeafterimg"
        class="before_img"
      />
      <h3  class="bigtext">Måske en fed ting eller 2?</h3>
    </div>
  </div>
</template>

<style scoped lang="scss">
.before_wrapper {
  background-color: green;
  padding: 50px var(--wrapper-padding-x);

  &.reverse {
    .bigtext {
      order: -1;
    }

    .before_img {
      order: 2;
    }
    h2 {
        text-align: right;
    }
    p {
        text-align: right;
    }
    .description_text {
        align-items: left;
    }

    .before_header {
      display: none;
    }
  }
}
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}



.bigtext {
  display: grid;
  align-items: center;
  font-size: 96px;
}
</style>
