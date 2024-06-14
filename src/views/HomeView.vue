<script setup>
import {
  getFirestore,
  collection,
  getDocs,
  updateDoc,
} from "firebase/firestore";
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

import boligblokImg from "@/components/icon/boligblok.jpg";
import perspektivImg from "@/components/icon/perspektiv.png";
import simonInterview from "@/components/icon/Simon.mp4";

import { ref, onMounted } from "vue";
import TwoColumnGrid from "@/components/TwoColumnGrid.vue";

import { initializeApp } from "firebase/app";
import firebaseConfig from "@/utils/db.js";

const poll = ref([]);
const app = initializeApp(firebaseConfig);

async function getPollResults() {
  const db = getFirestore(app);
  const dbPoll = collection(db, "poll");
  const poll = await getDocs(dbPoll);
  const pollResultList = poll.docs.map((doc) => {
    const id = doc.id;
    const data = doc.data();

    return {
      id,
      ...data,
    };
  });

  return pollResultList;
}

async function handleVote(vote) {
  const updatedVote = poll.value.find((item) => item.id === vote.id);
  updatedVote.votes++;

  try {
    await updateDoc(vote, updatedVote);
  } catch (e) {
    console.log("handleVote error:", e);
  }
}

onMounted(async () => {
  poll.value = await getPollResults();
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
          <TextMedia
            heading="OUH i dag"
            grid-heading="Byområdet midt i Odense skal have nyt liv"
            grid-text-top="I dag er OUH Fyns største arbejdsplads, men om nogle år, når hospitalet flytter adresse, vil der opstå mange nye muligheder. Området skal genanvendes og blive til noget nyt.
          Der er blevet bygget på området gennem mange år, med byggestile der passede til deres tid. Derfor står der mange forskellige bygninger på området, fra forskellige tidsperioder og stilarter. Hver bygning har sit eget potentiale for genanvendelse efter hospitalets flytning. "
            :grid-image-src="boligblokImg"
          />
        </template>
        <template #col-2>
          <TextMedia
            heading=""
            grid-heading="Drømme for fremtiden"
            grid-text-top="
            Vi har mange ideer og drømme for området, både nye ideer og ideer, der bevarer nogle af områdets skjulte skatte og de smukke originale bygningsværker. Samtidig tror vi på, at byens borgere skal have mulighed for at give deres input til, hvad der skal ske i det nye byområde, som om nogle år skal udvikles i Odense. <br/>
            Derfor vil vi allerede nu give muligheden for, at I kan komme med jeres ideer og drømme. <br/>
            Drømmer du om skønne boliger, grønne områder, sociale samlingssteder eller noget helt andet i dit nærområde? <br/>
            Så er det nu, du har muligheden for at få netop dine drømme inkluderet i udviklingen."
            :grid-image-src="perspektivImg"
            :reverse="true"
          />
        </template>
      </TwoColumnGrid>
    </section>
    <PageBreaker />
    <section id="interview_video">
      <TextMedia
        heading=""
        grid-heading="Simon fra Creo Arkitekter sætter nogle ord på projektet"
        grid-text-top=""
        grid-text-bottom="Kunne du forestille dig at bo i de flotte rødstensbygninger fra 1912? Eller måske en ny botanisk have lige midt i centrum"
        :grid-interview="simonInterview"
        :vertical="true"
      />
    </section>

    <section id="before_image">
      <BeforeAfterImg
        mainHeading=""
        reverseMainHeading=""
        subHeading="Rødstensbygninger fra da OUH først blev bygget i 1912, har potentiale til at danne rammerne for fantastiske hjem."
        bodyText=""
        bigText="Kunne du forestille dig at bo her?"
        :sliderImages="[]"
        :reverseSliderImages="[
          { src: afterImage1, title: '' },
          { src: afterImage2, title: '' },
        ]"
        :reverse="true"
      />

      <BeforeAfterImg
        mainHeading=""
        reverseMainHeading=""
        subHeading="Et vidensområde for Medicinstuderende bliver nu til et udendørs samlingspunkt, omringet af grønt."
        bodyText=""
        bigText="Hvad synes du?"
        :sliderImages="[
          { src: beforeImage1, title: '' },
          { src: beforeImage2, title: '' },
        ]"
      />
    </section>

    <section id="poll_text">
      <TwoColumnGrid second-column-width="1.5fr">
        <template #col-1>
          <TextBox />
        </template>

        <template #col-2>
          <PollBox @submit="handleVote" />
        </template>
      </TwoColumnGrid>
    </section>

    <CaruselSlider :slides="poll" />
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
