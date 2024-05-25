<script setup>
import { ref } from "vue";
import InputField from "@/components/input/InputField.vue";

const currentVote = ref(null);

function handleChange(value) {
  currentVote.value = value;
}

function submit() {
  console.log("jubii :-)");
}
</script>

<template>
  <div class="box_container">
    <h1 class="h2_poppins">
      Giv os din mening så vi kan være ligeglade med hvad du tænker!
    </h1>
    currentVote: {{ currentVote }}
    <form @submit.prevent="submit">
      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote"
        value="option 1"
        @changed="handleChange"
      />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote"
        value="option 2"
        @changed="handleChange"
      />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote"
        value="option 3"
        @changed="handleChange"
      />

      <InputField
        label="Lorem ipsum dolor, sit amet consectetur adipisicing elit. Illo ullam beatae ab commodi odio exercitationem?"
        name="vote"
        value="option 4"
        @changed="handleChange"
      />

      <button type="submit">Send</button>
    </form>
  </div>
</template>

<style scoped>
.box_container {
  display: grid;
  padding: 71px 71px 51px 154px;
  gap: 54px;
  background-color: #fefae0;
}

form {
  display: grid;
  gap: 36px;
}

button {
  width: max-content;
  margin-left: auto;
}
</style>
