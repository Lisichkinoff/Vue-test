<script setup lang="ts">
import { ref, computed, onMounted, onUnmounted } from 'vue';
import Header from "./components/Header.vue";
import Card from "./components/Card.vue";
import BlackSquare from "./components/BlackSquare.vue";
import CardSlider from "./components/CardSlider.vue";

const cards = [
  {
    title: "Solutions for people like you like people",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "none",
    bgColor: "bg-gray-300",
    buttonColor: "bg-cyan-400",
    tag: "CATEGORY | MARKETING",
    tagColor: "bg-cyan-500",
    author: "Adam Sandler",
    authorColor: "text-cyan-400",
  },
  {
    title: "Solutions for people like you like people",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "./home-pictures/sakura.png",
    bgColor: "bg-blue-100",
    buttonColor: "bg-cyan-400",
    tag: "CATEGORY",
    tagColor: "bg-cyan-500",
    author: "Adam Sandler",
    authorColor: "text-sky-400",
  },
  {
    title: "Solutions for people like",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "none",
    bgColor: "bg-pink-400",
    buttonColor: "bg-blue-900",
    tag: "CATEGORY | MARKETING",
    tagColor: "bg-blue-900",
    author: "Adam Sandler",
    authorColor: "text-sky-400",
  },
  {
    title: "Solutions for people like you like people",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "none",
    bgColor: "bg-cyan-500",
    buttonColor: "bg-blue-900",
    tag: "CATEGORY | MARKETING",
    tagColor: "bg-blue-900",
    author: "Adam Sandler",
    authorColor: "text-sky-400",
  },
  {
    title: "Solutions for people like",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "./home-pictures/camera.png",
    bgColor: "bg-purple-100",
    buttonColor: "bg-cyan-400",
    tag: "CATEGORY | MARKETING",
    tagColor: "bg-cyan-400",
    author: "Adam Sandler",
    authorColor: "text-sky-400",
  },
  {
    title: "Solutions for people like you like people",
    description:
      "How can we help your technology and services business develop a revenue engine based",
    image: "none",
    bgColor: "bg-gray-300",
    buttonColor: "bg-blue-900",
    tag: "CATEGORY",
    tagColor: "bg-blue-900",
    author: "Adam Sandler",
    authorColor: "text-sky-400",
  },
];

const windowWidth = ref(window.innerWidth);

const updateWindowWidth = () => {
  windowWidth.value = window.innerWidth;
};

const displayedCards = computed(() => {
  if (windowWidth.value <= 575) {
    return cards.slice(0, 2);
  } else if (windowWidth.value >= 576 && windowWidth.value <= 1199) {
    return cards.slice(0, 4);
  } else {
    return cards;
  }
});

onMounted(() => {
  window.addEventListener('resize', updateWindowWidth);
});

onUnmounted(() => {
  window.removeEventListener('resize', updateWindowWidth);
});
</script>

<template>
  <Header />
  <div
    class="flex flex-wrap justify-center gap-8 mx-auto max-w-screen-xl mb-20">
    <Card v-for="(card, index) in displayedCards" :key="index" v-bind="card" />
  </div>
  <BlackSquare />
   <CardSlider :cards="cards" />
</template>
