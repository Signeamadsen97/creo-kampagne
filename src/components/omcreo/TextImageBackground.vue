<script setup></script>

<template>
  <div class="wrapper">
    <h2 class="h2_poppins">Hero text</h2>
    <h2 class="h2_poppins">Hero text</h2>
    <div class="grid">
      <div class="text">
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aliquam
          deserunt suscipit blanditiis nihil nostrum possimus voluptatem sit
          exercitationem porro quibusdam quae velit, quis ullam aliquid
          provident, unde itaque. Consequatur necessitatibus dicta laborum rem
          corporis quo iusto! Ipsum, quos? Aliquam ullam corrupti pariatur
          recusandae repellat dicta, saepe animi et? Quod, assumenda!
        </p>
      </div>
      <div class="img">
        <img class="img_tib" src="https://fakeimg.pl/467x549" alt="" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.h2_poppins {
  text-align: center;
}

.wrapper {
  background-color: aqua;
  display: grid;
}

.img_tib {
  width: 100%;
}
</style>
