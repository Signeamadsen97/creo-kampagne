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

<style scoped lang="scss">
.break-square {
  width: 100%;
  height: 160px;
  background-color: #D4D4AA;
  position: relative;
  z-index: 0;
  margin-top: -50px;
  overflow: hidden;

  @media screen and (max-width: 900px) {
         height: 120px;
        }

  @media screen and (max-width: 400px) {
          height: 80px;
        }
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

  @media screen and (max-width: 900px) {
         font-size: 65px;
        }

  @media screen and (max-width: 400px) {
          font-size: 45px;
        }
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