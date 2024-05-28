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

import beforeImage1 from "@/components/icon/before1.jpg";
import afterImage1 from "@/components/icon/after1.jpg";
import beforeImage2 from "@/components/icon/before2.jpg";
import afterImage2 from "@/components/icon/after2.jpg";
import karreImage from "@/components/icon/karre.jpg"
import boligblokImage from "@/components/icon/boligblok.jpg"

import { ref, onMounted } from "vue";
import TwoColumnGrid from "@/components/TwoColumnGrid.vue";

import { initializeApp } from "firebase/app";
import firebaseConfig from "@/utils/db.js";

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
    text1: `Der er i alt`,
    text2: `som har stemt det samme som dig`,
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 1",
    },
    votes: 0,
  },
  {
    text1: `Der er i alt`,
    text2: `som har stemt det samme som dig`,
    votes: 0,
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 1",
    },
  },
  {
    text1: "Der er i alt",
    text2: `som har stemt det samme som dig`,
    votes: 0,
    image: {
      src: "https://fakeimg.pl/467x549",
      alt: "Billede 1",
    },
  },
  {
    text1: "Der er i alt",
    text2: `som har stemt det samme som dig`,
    votes: 0,
    image: {
      src: "https://fakeimg.pl/467x549",
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
          <TextMedia heading="OUH i dag og for fremtiden" grid-heading="Byområdet midt i Odense skal have nyt liv"
            grid-text-top="i dag er OUH fyns største arbejdsplads, men om nogen år når  hospitalet flytter adresse, bliver mulighederne er mange. Området skal genanvendes og blive til noget nyt. <br/>
            Der er på området blevet bygget over mnge år, i byggestilen so har passet til tiden. Derfor står der mange forskellige bygningskroppe på området, som hver har forskellige potentialer for genanvendelse efter hospitalets udrykning"
            :grid-image-src="boligblokImage" />
        </template>
        <template #col-2>
          <TextMedia heading="" grid-heading="Hvilke drømme har fremtiden naboer og beboere for området?"
            grid-text-top="Vi tror på at byens borgere skal have mulighed for at give deres holdninger til havd der skal ske "
            :grid-image-src="karreImage" :reverse="true" />
        </template>
      </TwoColumnGrid>
    </section>
    <PageBreaker />
    <section id="interview_video">
      <TextMedia heading="" grid-heading="Simon fra Creo Arkitekter sætter nogle ord på projektet" grid-text-top=""
        grid-text-bottom="Kunne du forestille dig at bo i de flotte rødstensbygninger fra 1912? Eller måske en ny botanisk have lige midt i centrum"
        grid-image-src="https://fakeimg.pl/774x516" :vertical="true" />
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
    <section id="before_image">
      <BeforeAfterImg mainHeading=""
        subHeading="Rødstensbygninger fra da OUH først blev bygget i 1912, har potentiale til at forme rammerne for fantastiske hjem."
        bodyText="" bigText="Kunne du forestille dig at bo her?" :beforeImage="beforeImage1" :afterImage="afterImage1" />

      <BeforeAfterImg :reverse="true" mainHeading=""
        subHeading="Et vidensområde for medicinstuderende bliver nu til et udendørs samlingspunkt omringet af grønt."
        bodyText="" bigText="Hvad synes du?" :beforeImage="beforeImage2" :afterImage="afterImage2" />
    </section>
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
