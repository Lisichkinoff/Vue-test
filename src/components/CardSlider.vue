<script setup lang="ts">
import { ref, computed, defineProps, watchEffect, onMounted, onUnmounted } from 'vue';
import Card from './Card.vue';

interface CardType {
  title: string;
  description: string;
  image: string;
  bgColor: string;
  buttonColor: string;
  tag: string;
  tagColor: string;
  author: string;
  authorColor: string;
}

const props = defineProps<{ cards: CardType[] }>();

const currentIndex = ref(0);
const cardsPerPage = ref(3);

const updateCardsPerPage = () => {
  const width = window.innerWidth;
  if (width < 576) {
    cardsPerPage.value = 1;
  } else if (width < 1200) {
    cardsPerPage.value = 2;
  } else {
    cardsPerPage.value = 3;
  }
};

watchEffect(() => {
  updateCardsPerPage();
});

onMounted(() => {
  window.addEventListener('resize', updateCardsPerPage);
});

onUnmounted(() => {
  window.removeEventListener('resize', updateCardsPerPage);
});

const visibleCards = computed(() => {
  return props.cards.slice(currentIndex.value, currentIndex.value + cardsPerPage.value);
});

const canGoBack = computed(() => currentIndex.value > 0);
const canGoForward = computed(() => currentIndex.value + cardsPerPage.value < props.cards.length);

const goBack = () => {
  if (canGoBack.value) {
    currentIndex.value -= cardsPerPage.value;
  }
};

const goForward = () => {
  if (canGoForward.value) {
    currentIndex.value += cardsPerPage.value;
  }
};

</script>

<template>
  <div class="mb-20">
    <div class="flex flex-wrap justify-center gap-8 mx-auto max-w-screen-xl mb-10">
      <Card v-for="(card, index) in visibleCards" :key="index" v-bind="card" />
    </div>
    <div class="controls flex mt-4 max-w-screen-xl mx-auto px-1">
      <button
        @click="goBack"
        :disabled="!canGoBack"
        class="px-5 text-sky-500 text-5xl"
      >
        <
      </button>
      <button
        @click="goForward"
        :disabled="!canGoForward"
        class="px-5 text-sky-500 text-5xl"
      >
        >
      </button>
    </div>
  </div>
</template>

<style scoped>

@media (max-width: 575px) {
  .controls {
    justify-content: center;
  }
}
.controls button:disabled {
  color: black;
  cursor: not-allowed;
}


</style>