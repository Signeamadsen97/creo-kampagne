<script setup>
const props = defineProps({
  reverse: {
    type: Boolean,
    default: false,
  },
  vertical: {
    type: Boolean,
    default: false,
  }
});

</script>

<template>
  <div class="media_wrapper" :class="{ reverse: reverse, vertical: vertical}">
    <h1 class="media_heading">Om projekt</h1>
    <div class="grid">
      <div class="media_text">
        <h2>Køb 2 elefanter for 1</h2>
        <p>
          Lorem Ipsum is simply dummy text of the printing and typesetting
          industry. Lorem Ipsum has been the industry's standard dummy text ever
          since the 1500s,
        </p>
      </div>
      <img src="https://fakeimg.pl/467x549" alt="" class="media_img" />
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

    .media_heading {
      display: none;
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
