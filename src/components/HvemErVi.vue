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
    <ul class="list">
      <li class="list__item" v-for="(profile, index) in profiles" :key="`profile-${index}`">
        <img class="list__img" :src="profile.img" alt="" />
        <p class="list__text">{{ profile.text }}</p>
      </li>
    </ul>
  </div>
</template>

<style scoped lang="scss">
.list {
  list-style: none;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 50px;
  padding: 0;
  margin: 0 auto;
  width: 80%;
  max-width: 1262px;

  &__img {
    border-radius: 50%;
    aspect-ratio: 1;
    max-width: 319px;
    width: 80%;
    display: block;
    margin: 0 auto;
  }
}
</style>
