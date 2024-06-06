<script setup>
const props = defineProps({
  label: {
    type: String,
    default: "",
  },
  name: {
    type: String,
    default: "",
  },
  value: {
    type: String,
    default: "",
  },
});
</script>

<template>
  <label class="body_poppins input">
    <input type="radio" :name="name" @change="$emit('changed', $event.target.value)" :value="value" />
    <div class="radio"></div>
    <span class="text"> {{ label }} </span>
  </label>
</template>

<style scoped lang="scss">
.input {
  display: flex;
  align-items: center;
  gap: 30px;
}

input[type="radio"] {
  display: none;

  &:checked {
    ~.radio::after {
      display: block;
    }
  }
}

.radio {
  height: 20px;
  width: 20px;
  background: green;
  border-radius: 50%;
  flex-shrink: 0;
  display: flex;
  justify-content: center;
  align-items: center;

  &::after {
    content: "";
    height: 10px;
    width: 10px;
    background: #EDB458;
    display: block;
    border-radius: 50%;
    display: none;
  }
}

label {
  font-size: 20px;
  font-weight: 100;
}
@media screen and (max-width: 450px) {
  .input {
    gap: 15px; /* Reducer gap for mindre skærme */
  }

  .radio {
    height: 15px;
    width: 15px;

    &::after {
      height: 7px;
      width: 7px;
    }
  }

  label {
    font-size: 16px; /* Reducer font-størrelse for mindre skærme */
  }
}
</style>
