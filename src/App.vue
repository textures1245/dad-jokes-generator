<script>
</script>

<script setup>
import { ref } from "vue";
import HeaderApp from "./components/Header.vue";
import JokeCard from "./components/JokeCard.vue";
let cardList = ref(0);
</script>

<template>
  <div class="my-4 rm-my">
    <div class="vh-100 mw-100 border-e7e7e7">
      <HeaderApp></HeaderApp>

      <template> </template>
      <!-- body -->
      <div class="container-sm mw-50 mh-100">
        <div
          class="my-4 d-flex justify-content-center gap-3 fw-light fs-6 align-items-center"
        >
          <button @click="cardList++" class="btn btn-sm btn-outline-primary">
            Give me a joke!
          </button>
          |
          <button
            @click="cardList = 0"
            class="btn btn-sm btn-outline-danger reset"
          >
            Reset
          </button>
        </div>

        <div class="d-flex flex-column align-items-center gap-4">
          <JokeCard v-for="card in cardList" :key="card"></JokeCard>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@media only screen and (max-width: 768px) {
  .border-w {
    border-width: 0px;
  }

  .rm-my {
    margin-top: 0 !important;
    margin-bottom: 0 !important;
  }
}
</style>
