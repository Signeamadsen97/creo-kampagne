<script setup>
import { getFirestore, collection, getDocs } from "firebase/firestore";
import Hero from "@/components/Hero.vue";
import BrandValue from "@/components/BrandValue.vue";
import TextMedia from "@/components/TextMedia.vue";
import PageBreaker from "@/components/PageBreaker.vue";
import TextBox from "@/components/TextBox.vue";
import PollBox from "@/components/PollBox.vue";
import CaruselSlider from "@/components/CaruselSlider.vue";
import BeforeAfterImg from "@/components/BeforeAfterImg.vue";


import afterImage1 from "@/components/icon/after-img1.jpg";
import afterImage2 from "@/components/icon/after-img2.png";

import beforeImage1 from "@/components/icon/before-img1.jpg";
import beforeImage2 from "@/components/icon/before-img2.png";

import perspektivImage from "@/components/icon/perspektiv.png";
import boligIkon from "@/components/icon/house-ikon.svg";
import groentIkon from "@/components/icon/tree-ikon.svg";
import genanvendelseIkon from "@/components/icon/reuse.svg";
import socialIkon from "@/components/icon/social-icon.svg"

import { ref, onMounted } from "vue";
import TwoColumnGrid from "@/components/TwoColumnGrid.vue";

import { initializeApp } from "firebase/app";
import firebaseConfig from "@/utils/db.js";
import { Icon } from "vue3-carousel";

const poll = ref();
const app = initializeApp(firebaseConfig);
const db = getFirestore(app);

async function getPollResults() {
  const db = getFirestore(app);
  const dbPoll = collection(db, "poll");
  const poll = await getDocs(dbPoll);
  const pollResultList = poll.docs.map((doc) => doc.data());

  return pollResultList;
}

const items = ref([
  {
    text1: `I alt`,
    text2: `personer drømmer om boliger`,
    image: {
      src: boligIkon,
      alt: "Billede 1",
    },
    votes: 0,
  },
  {
    text1: `I alt`,
    text2: `drømmer om grønne områder`,
    votes: 0,
    image: {
      src: groentIkon,
      alt: "Billede 1",
    },
  },
  {
    text1: "I alt",
    text2: `drømmer om genanvendele og bæredygtighed`,
    votes: 0,
    image: {
      src: genanvendelseIkon,
      alt: "Billede 1",
    },
  },
  {
    text1: "I alt",
    text2: `drømmer om sociale samlingsområder`,
    votes: 0,
    image: {
      src: socialIkon,
      alt: "Billede 1",
    },
  },
]);

function calculateVotes(votes) {
  votes.map((vote) => {
    switch (vote.vote) {
      case "option 1":
        items.value[0].votes++;
        break;
      case "option 2":
        items.value[1].votes++;
        break;
      case "option 3":
        items.value[2].votes++;
        break;
      case "option 4":
        items.value[3].votes++;
        break;
      default:
        break;
    }
  });
}

function handleVote(vote) {
  switch (vote) {
    case "option 1":
      items.value[0].votes++;
      break;
    case "option 2":
      items.value[1].votes++;
      break;
    case "option 3":
      items.value[2].votes++;
      break;
    case "option 4":
      items.value[3].votes++;
      break;
    default:
      break;
  }
}

onMounted(async () => {
  const votes = await getPollResults();
  calculateVotes(votes);
});
</script>

<template>
  <main>
    <section id="introduction_video">
      <div class="wrapper">
        <Hero />
      </div>
    </section>
    <BrandValue />
    <section id="about_project">
      <TwoColumnGrid>
        <template #col-1>
          <TextMedia heading="OUH i dag" grid-heading="Byområdet midt i Odense skal have nyt liv"
            grid-text-top="i dag er OUH fyns største arbejdsplads, men om nogen år når  hospitalet flytter adresse, bliver mulighederne er mange. Området skal genanvendes og blive til noget nyt. <br/>
            Der er på området blevet bygget over mange år, i den byggestilen so har passet til tiden. Derfor står der mange forskellige bygningskroppe på området, fra forskellige tider og stilarter. Alle bygningerne har forskellige potentialer for genanvendelse efter hospitalets udrykning. "
            grid-image-src="src/components/Icon/boligblok.jpg" />
        </template>
        <template #col-2>
          <TextMedia heading="" grid-heading="Drømme for fremtiden" grid-text-top="
            Vi har mange ideer og drømme for området, både nye ideer og ideer som bevare nogen af området skjulte skatte og de smukke originale bygningsværker. Samtidig mender vi tror på at byens borgere skal have mulighed for at give deres ideer til hvad der skal ske på det nye byområde, som om nogen år skal udvikles i Odense. <br/>
            Derfor vil vi give muligheden for allerede nu at i kan komme med jeres ideer og drømme. <br/> 
            Drømmer du om skønne boliger, Grønne områder, sociale samlings steder eller noget helt andet, i dit nærområde? <br/>
            Så er det nu og her du kan få muligheden for at netop dine drømme bliver inkluderet i udviklingen."
            :grid-image-src="perspektivImage" :reverse="true" />
        </template>
      </TwoColumnGrid>
    </section>
    <PageBreaker />
    <section id="interview_video">
      <TextMedia heading="" grid-heading="Simon fra Creo Arkitekter sætter nogle ord på projektet" grid-text-top=""
        grid-text-bottom="Kunne du forestille dig at bo i de flotte rødstensbygninger fra 1912? Eller måske en ny botanisk have lige midt i centrum"
        grid-interview="src/components/icon/Simon.mp4" :vertical="true" />
    </section>

    <section id="before_image">
      <BeforeAfterImg mainHeading="" reverseMainHeading=""
        subHeading="Rødstensbygninger fra da OUH først blev bygget i 1912, har potentiale til at danne rammerne for fantastiske hjem."
        bodyText="" bigText="Kunne du forestille dig at bo her?" :sliderImages="[
        ]" :reverseSliderImages="[
  { src: afterImage1, title: '' },
  { src: afterImage2, title: '' },
]" :reverse="true" />


      <BeforeAfterImg mainHeading="" reverseMainHeading=""
        subHeading="Et vidensområde for Medicinstuderende bliver nu til et udendørs samlingspunkt, omringet af grønt."
        bodyText="" bigText="Hvad synes du?" :sliderImages="[
          { src: beforeImage1, title: '' },
          { src: beforeImage2, title: '' },
        ]" />
    </section>

    <section id="poll_text">
      <TwoColumnGrid second-column-width="1.5fr">
        <template #col-1>
          <TextBox />
        </template>

        <template #col-2>
          <PollBox @vote="handleVote" />
        </template>
      </TwoColumnGrid>
    </section>

    <CaruselSlider :slides="items" />
  </main>
</template>

<style scoped lang="scss">
.text-media-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.poll-grid {
  display: grid;
  grid-template-columns: 1fr 1.5fr;
}
</style>
