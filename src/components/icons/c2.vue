<template>
  <div>
    <h2>C2 page</h2>
    <div>
      <li v-for="img in image" :key="img">
        <img :src="img.avatar_url" />
        {{ img.login }}
      </li>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";
console.log("finish");
const image = ref("");
const data = async function () {
  const dataGithub = await fetch("https://api.github.com/users");
  const jsonData = await dataGithub.json();
  image.value = jsonData;
  jsonData.forEach((item) => {
    console.log(item);
  });
};

const showValue = () => {
  for (let i = 0; i < 1000; i++) {
    console.log("i");
  }
};

const display = async () => {
  data();

  showValue();
};

display();
</script>

<style scoped></style>
