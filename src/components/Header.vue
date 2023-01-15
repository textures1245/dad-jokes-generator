<script>
</script>

<script setup>
import MOCK_NAME_DATA from "../assets/MOCK_JSON/MOCK_DATA.json";
const avatarApi = "https://api.dicebear.com/5.x/big-smile/png?seed=";
let name = null;
const genSeeds = () => {
  name = MOCK_NAME_DATA[Math.floor(Math.random() * 100)]["first_name"];
  return avatarApi + name;
};

const desc = `
  Applcation name: Dadjokes Generator
  Application playground:
  **ผลงานชี้นนี้จำทำเพื่อเสนออาจาร์ย อาจารย์อรรถวิท ชังคมานนท์ รายวิชาการพัฒนาโปรแกรมประยุกต์บนเว็บ**`;
</script>

<template>
  <nav>
    <nav class="rounded container-md navbar navbar-light bg-e7e7e7">
      <div class="container-fluid">
        <div class="d-flex justify-content-start gap-2 align-items-center">
          <img class="avatar-size" :src="genSeeds()" alt="" />
          <a class="navbar-brand text-black" href="#">DadJokes </a>
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
            <li style="font-size: 15px" class="fw-light my-2 mx-4">
              <b>Applcation name:</b> Dadjokes Generator <br />
              <b>Application playground:</b> Generator randoms jokes with limit
              at 50 jokes per days. <br />
              <b>API Using:</b> Dadjokes and DiceBear API <br />
              <b>
                **ผลงานชี้นนี้จำทำเพื่อเสนออาจาร์ย อาจารย์อรรถวิท ชังคมานนท์
                รายวิชาการพัฒนาโปรแกรมประยุกต์บนเว็บ</b
              > <br>
              <b>นายไตรภาค สิทธิแก้ว 6404101318</b>
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
