<script setup>
const props = defineProps({
  profiles: {
    type: Array,
    default: () => [],
  },
});
</script>

<template>
  <div class="wrapper">
    <h1 class="h1_poppins">Profiler fra Creo</h1>
    <ul class="list">
      <li
        class="list__item"
        v-for="(profile, index) in profiles"
        :key="`profile-${index}`"
      >
        <img class="list__img" :src="profile.img" alt="" />
        <p class="list__text body_poppins">{{ profile.text }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped lang="scss">

.h1_poppins {
  padding-top: 60px;
  text-align: center;
  padding-bottom: 100px;
}
.list {
  list-style: none;
  display: grid;
  grid-template-columns: 50% 50%;
  gap: 70px;
  padding: 0;
  margin: 0 auto;
  width: 80%;
  max-width: 1262px;

  @media screen and (max-width: 800px) {
    grid-template-columns: 1fr;
  }

  &__img {
    border-radius: 50%;
    aspect-ratio: 1;
    max-width: 319px;
    width: 80%;
    display: block;
    margin: 0 auto;
  }

  &__text {
    font-size: 40px;
    text-align: center;
    font-weight: 600;
    color: #606c38;
    &::before,
    &::after {
      content: "";
      display: block;
      height: 55px;
      width: 55px;
      background-image: url("../icon/Quote.png");
      background-size: 100%;
    }

    &::after {
      margin-left: auto;
    }
  }
}
</style>
