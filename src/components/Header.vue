<script>
import MOCK_NAME_DATA from "../assets/MOCK_JSON/MOCK_DATA.json";

export default {
  data() {
    return {
      name: MOCK_NAME_DATA[Math.floor(Math.random() * 10)]["first_name"],
    };
  },
};
</script>

<script setup>
import { createAvatar } from "@dicebear/core";
import { bigSmile } from "@dicebear/collection";

const avatarUrl = () => {};
</script>

<template>
  <nav>
    <nav class="rounded container-lg navbar navbar-light bg-e7e7e7">
      <div class="container-fluid">
        <div class="d-flex justify-content-start gap-2 align-items-center">
          <img
            class="avatar-size"
            :src="`https://api.dicebear.com/5.x/big-smile/png?seed=${name}`"
            alt=""
          />
          <a class="navbar-brand" href="#">DadJoke </a>
        </div>

        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarScroll"
          aria-controls="navbarScroll"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarScroll">
          <ul
            class="navbar-nav me-auto my-2 my-lg-0 navbar-nav-scroll"
            style="--bs-scroll-height: 100px"
          >
            <li class="fw-light my-20">
              Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nihil
              nemo possimus laboriosam aliquid saepe harum minus iste,
              repudiandae sapiente nesciunt debitis reprehenderit doloribus
              pariatur itaque quas natus dignissimos cupiditate praesentium?
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </nav>
</template>

<style scoped>
.avatar-size {
  width: 20%;
}
</style>
