<script setup>
import HeaderApp from "./components/Header.vue";
</script>

<template>
  <div class="my-4 rm-my">
    <div class="vh-100 mw-100 border-e7e7e7">
      <Suspense>
        <HeaderApp></HeaderApp>
      </Suspense>
      <template>
      </template>
      <!-- body -->
      <div class="container-lg">
        <div
          style="height: 10vh"
          class="d-flex justify-content-center gap-3 fw-light fs-6 align-items-center"
        >
          <button class="btn btn-sm btn-outline-primary">
            Give me a joke!
          </button>
          |
          <button class="btn btn-sm btn-outline-danger reset">Reset</button>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
@media only screen and (max-width: 600px) {
  .border-w {
    border-width: 0px;
  }

  .rm-my {
    margin-top: 0 !important;
    margin-bottom: 0 !important;
  }
}
</style>
