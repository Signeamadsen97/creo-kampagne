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
          <TextMedia
            heading="Om os"
            grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
            grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
            grid-image-src="https://fakeimg.pl/467x549"
          />
        </template>
        <template #col-2>
          <TextMedia
            heading=""
            grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
            grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
            grid-image-src="https://fakeimg.pl/467x549"
            :reverse="true"
          />
        </template>
      </TwoColumnGrid>
    </section>
    <PageBreaker />
    <section id="interview_video">
      <TextMedia
        heading=""
        grid-heading="Lorem ipsum dolor sit amet consectetur adipisicing elit. Quos, minus."
        grid-text-top="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-text-bottom="Lorem ipsum dolor sit amet consectetur, adipisicing elit. Distinctio vel eius aperiam dicta, consequatur debitis accusantium, eaque voluptates ullam facilis reiciendis commodi ducimus dolorum! Asperiores quasi quas ipsum, repellat ut, nostrum, reiciendis minima id consectetur vel saepe nemo odio est. Aliquam dolore consequuntur consequatur, natus in perspiciatis magnam expedita atque?"
        grid-image-src="https://fakeimg.pl/774x516"
        :vertical="true"
      />
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
      <BeforeAfterImg
        mainHeading=""
        subHeading="Charmerende lejligheder i de gamle rødstensbygninger"
        bodyText="Kunne du forestille dig at bo i en af de tidligste hospitalsbygninger. De gamle smukke rødstenbygninger har potentiale til at forme rammerne for at fantastisk hjem, midt i byen nær mange grønne områder,"
        bigText="Kunne du forestille dig at bo her?"
        :beforeImage="beforeImage1"
        :afterImage="afterImage1"
      />

      <BeforeAfterImg
        :reverse="true"
        mainHeading=""
        subHeading="Nyd din kaffe under blåregnen"
        bodyText="Områderne omkring det gamle hospital byder på mange muligheder. blandt andet denne smukke plads, som med fordel kunne blive en cafe eler et samlingsområde. Her kunne man nyde sin, frkost, kaffe eller andet, under den smukke blåregn"
        bigText="Kunne du forestille dig at drikke din kaffe her?"
        :beforeImage="beforeImage2"
        :afterImage="afterImage2"
      />
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
