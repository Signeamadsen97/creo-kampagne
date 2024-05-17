<script setup></script>

<template>
  <div class="box_container">
    <h1>Giv os din mening så vi kan være ligeglade med hvad du tænker!</h1>

    <form>
      <label><input type="radio" />Lorem Ipsum is simply dummy text of the printing</label>
      <label><input type="radio" />Lorem Ipsum is simply dummy text of the printing</label>
      <label><input type="radio" />Lorem Ipsum is simply dummy text of the printing</label>

      <button type="submit">Send</button>
    </form>
  </div>
</template>

<style scoped>
.box_container {
  display: grid;
  padding: 71px 71px 51px 154px;
  gap: 54px;
  background-color: #FEFAE0;

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
