<script setup>
import { ref } from "vue";
import MOCK_NAME_DATA from "../assets/MOCK_JSON/MOCK_DATA.json";

let likes = ref(0);
let dislikes = ref(0);

//* avatar-api
const avatarApi = "https://api.dicebear.com/5.x/big-smile/png?seed=";
let avatarName = null;
let mouthOpt = null;
const genSeeds = () => {
  avatarName = MOCK_NAME_DATA[Math.floor(Math.random() * 100)]["first_name"];
  return mouthOpt !== null
    ? avatarApi + avatarName + `&mouth=${mouthOpt}`
    : avatarApi + avatarName;
};
</script>

<script>
import axios from "axios";
const options = {
  method: "GET",
  url: "https://dad-jokes.p.rapidapi.com/random/joke",
  headers: {
    "X-RapidAPI-Key": "84214a2573msh8eef85f0805fb7bp11f306jsn01780e8a3986",
    "X-RapidAPI-Host": "dad-jokes.p.rapidapi.com",
  },
};
export default {
  data() {
    return {
      joke: {
        setup: null,
        punchline: null,
      },
    };
  },
  async mounted() {
    const res = await axios.request(options);
    this.joke.setup = res.data.body[0].setup;
    this.joke.punchline = res.data.body[0].punchline;
  },
};
</script>
<template>
  <div
    style="height: 10rem; max-height: 10rem; min-height: 16rem"
    class="resize-card row col-11"
  >
    <div
      class="col-3 d-flex justify-content-center align-items-center border border-1"
    >
      <img
        :src="genSeeds()"
        class="bg-e7e7e7 rounded rounded-pill border mw-75 mh-75"
        alt=""
      />
    </div>
    <div class="text-box col-9 d-flex flex-column border border-1">
      <div style="flex-basis: 25%" class="d-flex gap-2">
        <small>{{ avatarName }}</small>
        <span>·</span>
        <span style="font-size: 12px" class="text-muted">24/20/6888</span>
      </div>
      <div style="flex-basis: 55%" class="align-items-start">
        <small class="fw-bold">
          {{
            joke.punchline ? joke.punchline : "DadJokes API had got over limit."
          }}
          <br />
          {{
            joke.setup
              ? joke.setup
              : `
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Iste beatae
          nihil inventore, culpa.`
          }}
        </small>
      </div>
      <div
        style="flex-basis: 30%"
        class="text-end d-flex gap-3 justify-content-between"
      >
        <div
          style="font-size: 13px"
          class="d-flex flex-columns gap-2 text-muted"
        >
          <small
            >likes: <b>{{ likes }}</b></small
          >
          <small
            >dislikes: <b>{{ dislikes }}</b>
          </small>
        </div>
        <div class="d-flex flex-columns gap-3">
          <button
            type="button"
            @click="likes++, (mouthOpt = 'openedSmile')"
            class="btn d-flex gap-2 btn-sm btn-outline-warning px-2"
          >
            <lottie-player
              src="https://assets7.lottiefiles.com/datafiles/DQs1NxxhARpqrOe/data.json"
              background="transparent"
              speed="1"
              style="width: 20px"
              loop
              autoplay
            ></lottie-player
            >Like
          </button>
          <button
            type="button"
            @click="dislikes++, (mouthOpt = 'unimpressed')"
            class="d-flex gap-2 btn btn-sm btn-outline-secondary px-2"
          >
            <lottie-player
              src="https://assets9.lottiefiles.com/packages/lf20_pojzngga.json"
              background="transparent"
              speed="1"
              style="width: 20px"
              loop
              autoplay
            ></lottie-player>
            Sad
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
.text-box > div {
  display: flex;
  align-items: center;
}

@media only screen and (max-width: 1000px) {
  .resize-card {
    min-height: auto !important;
  }
}
</style>
