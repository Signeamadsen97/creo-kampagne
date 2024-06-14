<script setup>
import { onBeforeUnmount, onMounted, ref } from "vue";

const playButton = ref(null);
const video = ref(null);
const transparentOverlay = ref(null);

function playVideo(event) {
  if (!video.value || !playButton.value || !transparentOverlay.value) return;
  event.preventDefault(); // Forhindre standard klik-handling
  video.value.play();
  playButton.value.style.display = "none"; // Skjul play-knappen, når videoen afspilles
  transparentOverlay.value.style.display = "none"; // Skjul gradient-overlay, når videoen afspilles
}

function pauseVideo() {
  if (!playButton.value || !transparentOverlay.value) return;
  playButton.value.style.display = "block"; // Vis play-knappen igen, hvis videoen pauses
  transparentOverlay.value.style.display = "block"; // Vis gradient-overlay igen, hvis videoen pauses
}

function hideOverlay() {
  if (!transparentOverlay.value) return;
  transparentOverlay.value.style.display = "none"; // Skjul gradient-overlay, når videoen afspilles
}
</script>

<template>
  <div class="grid">
    <div>
      <p class="body_poppins">
        Området ved “det gamle OUH”, som I kender det nu, vil skulle ombygges.
        Det bliver en helt ny bydel i Odense. Det er din by og derfor er det
        vigtigt, at høre din mening.
      </p>
    </div>

    <div>
      <h1 class="hero_1 h1_poppins">Boulevarden Odense</h1>
      <div class="video_container">
        <div class="container">
          <a href="#" class="playBut" ref="playButton" @click="playVideo">
            <!-- Generator: Adobe Illustrator 19.0.0, SVG Export Plug-In  -->
            <svg
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              xmlns:xlink="http://www.w3.org/1999/xlink"
              xmlns:a="http://ns.adobe.com/AdobeSVGViewerExtensions/3.0/"
              x="0px"
              y="0px"
              width="100%"
              height="200px"
              viewBox="0 0 213.7 213.7"
              enable-background="new 0 0 213.7 213.7"
              xml:space="preserve"
            >
              <polygon
                class="triangle"
                fill="none"
                stroke-width="7"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-miterlimit="10"
                points="
  73.5,62.5 148.5,105.8 73.5,149.1 "
              />

              <circle
                class="circle"
                fill="none"
                stroke-width="7"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-miterlimit="10"
                cx="106.8"
                cy="106.8"
                r="103.3"
              />
            </svg>
          </a>
        </div>
        <div class="transparent-overlay" ref="transparentOverlay"></div>
        <video
          ref="video"
          controls
          @pause="pauseVideo"
          @play="playVideo, hideOverlay"
        >
          <source class="banner-video" src="./icon/Banner_video.mp4" />
        </video>
        <h1 class="hero_2 h1_poppins">Dit nye område midt i byen</h1>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.grid {
  display: grid;
  grid-template-columns: 19.95841995841996dvw 68.05266805266805dvw;
  gap: 3.049203049203049dvw;
  padding-bottom: 8rem;
  margin-top: 50px;

  @media screen and (max-width: 850px) {
    display: flex;
    flex-direction: column-reverse;
  }
  @media screen and (max-width: 500px) {
    margin-top: 0px;
    padding-bottom: 10px;
  }
}

.heromedia {
  width: 100%;
  z-index: 0;
}

.body_poppins {
  padding-top: 10rem;
  font-weight: 400;
  font-size: 25px;
  color: black;

  @media screen and (max-width: 1200px) {
    display: grid;
    grid-template-columns: 1fr;
    padding-top: 70px;
    order: 2;
  }

  @media screen and (max-width: 850px) {
    display: grid;
    grid-template-columns: 1fr;
    padding-top: 30px;
    order: 2;
  }
  @media screen and (max-width: 500px) {
    font-size: 15px;
    margin-top: 20px;
  }
}

.hero_1 {
  //position: absolute;
  //margin-left: -3rem;
  //left: 50%;
  //transform: translate(-50%, -50%);
  //z-index: 2;

  @media screen and (max-width: 1200px) {
    display: grid;
    transform: none;
    left: auto;
    text-align: start;
    font-size: 25px;
  }
  @media screen and (max-width: 500px) {
    font-size: 20px;
  }
}

.hero_2 {
  position: absolute;
  right: 0;
  // margin-right: 1rem;
  // margin-top: -49px;

  @media screen and (max-width: 1200px) {
    display: grid;
    transform: none;
    left: auto;
    text-align: start;
    font-size: 25px;
    //margin-top: -39px;
  }

  @media screen and (max-width: 500px) {
    font-size: 20px;
  }
}

.banner-video {
  width: 100%;
  max-width: 1300px;
  height: auto;
  display: block;
  z-index: -1;
  margin-left: auto;
  margin-right: auto;

  &::before {
    content: "before";
  }
}

.container {
  width: 100%;
  text-align: center;
}

.circle {
  stroke: #0f9f55;
  stroke-dasharray: 650;
  stroke-dashoffset: 650;
  -webkit-transition: all 0.5s ease-in-out;
  opacity: 0.3;
}

.playBut {
  /*  border: 1px solid red;*/
  display: inline-block;
  -webkit-transition: all 0.5s ease;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;

  .triangle {
    -webkit-transition: all 0.7s ease-in-out;
    stroke-dasharray: 240;
    stroke-dashoffset: 480;
    stroke: #000;
    transform: translateY(0);
  }

  &:hover {
    .triangle {
      stroke-dashoffset: 0;
      opacity: 1;
      stroke: #0f9f55;
      animation: nudge 0.7s ease-in-out;

      @keyframes nudge {
        0% {
          transform: translateX(0);
        }
        30% {
          transform: translateX(-5px);
        }
        50% {
          transform: translateX(5px);
        }
        70% {
          transform: translateX(-2px);
        }
        100% {
          transform: translateX(0);
        }
      }
    }

    .circle {
      stroke-dashoffset: 0;
      opacity: 1;
    }
  }
}

.video_container {
  position: relative;
}

video {
  width: 100%;
  height: auto;
  display: block;
}

.transparent-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: rgba(255, 255, 255, 0.3); /* Halvtransparent hvid */
  z-index: 1;
  pointer-events: none;
}
</style>
