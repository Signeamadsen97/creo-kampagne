<script setup>
import { ref } from "vue";
import InputField from "@/components/input/InputField.vue";
import { getFirestore, setDoc, doc } from "firebase/firestore";
// Import the functions you need from the SDKs you need
import { initializeApp } from "firebase/app";
import firebaseConfig from "@/utils/db.js";
import { v4 as uuidv4 } from "uuid";

const emit = defineEmits(["vote"]);

const app = initializeApp(firebaseConfig);
const db = getFirestore(app);
const currentVote = ref(null);

function handleChange(value) {
  currentVote.value = value;
}

async function submit() {
  try {
    await setDoc(doc(db, "poll", uuidv4()), {
      vote: currentVote.value,
    });
  } catch (e) {
    console.warn("error", e);
  }

  emit("vote", currentVote.value);
  alert("Din stemme er indsendt 😊");
}
</script>

<template>
  <div class="box_container">
    <h1 class="h2_poppins">
      Hvad drømmer du om?
    </h1>
    <form @submit.prevent="submit">
      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote" value="option 1" @changed="handleChange" />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote" value="option 2" @changed="handleChange" />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote" value="option 3" @changed="handleChange" />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote" value="option 4" @changed="handleChange" />
      <div class="buttonwrapper">
        <button type="submit">Giv os din mening her!</button>
      </div>
    </form>
  </div>
</template>

<style scoped>
.box_container {
  display: grid;
  padding: 71px 71px 51px 154px;
  gap: 54px;
  background-color: #fefae0;
  width: 100%;
}

form {
  display: grid;
  gap: 36px;
  width: 100%;
}

.buttonwrapper {
  width: 100%;
  display: flex;
  justify-content: end;
}

button {
  background-clip: padding-box;
  background-color: #edb458;
  border: 1px solid transparent;
  border-radius: 0.25rem;
  box-shadow: rgba(0, 0, 0, 0.02) 0 1px 3px 0;
  box-sizing: border-box;
  color: black;
  cursor: pointer;
  display: inline-flex;
  font-family: system-ui, -apple-system, system-ui, "Helvetica Neue", Helvetica,
    Arial, sans-serif;
  font-size: 16px;
  font-weight: 600;
  justify-content: center;
  line-height: 1.25;
  margin: 0;
  min-height: 3rem;
  padding: calc(0.875rem - 1px) calc(1.5rem - 1px);
  position: relative;
  text-decoration: none;
  transition: all 250ms;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
  vertical-align: baseline;
  width: auto;
}

button:hover,
button:focus {
  background-color: #fb8332;
  box-shadow: rgba(0, 0, 0, 0.1) 0 4px 12px;
}

button:hover {
  transform: translateY(-1px);
}

button:active {
  background-color: #c85000;
  box-shadow: rgba(0, 0, 0, 0.06) 0 2px 4px;
  transform: translateY(0);
}
</style>
