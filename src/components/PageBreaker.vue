<script setup>
</script>

<template>
  <div class="break-square">
    <div class="content">
      <div class="marquee h1_poppins">
        <span>BOULEVARDEN - DIT NYE BYOMRÅDE I ODENSE</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.break-square {
  width: 100%;
  height: 325px;
  background-color: #D4D4AA;
  position: relative;
  z-index: 0;
  margin-top: -50px;
  overflow: hidden;
}

.marquee {
  white-space: nowrap;
  overflow: hidden;
  position: absolute;
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
}

.marquee span {
  display: inline-block;
  animation: marquee 13s linear infinite;
  font-size: 7rem;
}

@keyframes marquee {
  0% {
    transform: translateX(100%);
  }

  100% {
    transform: translateX(-100%);
  }
}
</style>