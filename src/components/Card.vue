<script setup lang="ts">
interface CardProps {
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

defineProps<CardProps>();
</script><template>
<div class="card p-4 border border-gray-300 shadow-lg bg-white flex flex-col justify-between mx-[10px]">
  <div
    :class="['absolute transform translate-y-[-10px] -ml-4 px-6 py-2 z-10', tagColor, 'text-white text-sm']"
  >
    {{ tag }}
  </div>
  <div
  :class="{
    'w-full h-42 flex items-center justify-center': true,
    [bgColor]: image === 'none'
  }"
>
    <img
      v-if="image !== 'none'"
      :src="image"
      alt="Card image"
      class="w-full h-full object-cover"
    />
    <span v-else class="text-gray-500"></span>
  </div>
  <div v-if="author" :class="['mt-2 font-thin', authorColor, 'font-semibold']">
    {{ author }}
  </div>
  <h2 class="text-lg font-bold mt-2">{{ title }}</h2>
  <p class="text-sm text-gray-700">{{ description }}</p>
  <button :class="['mt-20 px-4 py-2 w-45', buttonColor, 'text-white']">
    <a href="">Call to action</a>
  </button>
</div>
</template>


<style scoped>
@layer utilities {
  @media (max-width: 575px) {
    .card {
      width: calc(100% - 40px);
      height: 480px;
    }
  }
   @media (min-width: 576px) {
    .card {
      width: calc(50% - 60px);
      height: 480px;
    }
  }

  @media (min-width: 1200px) {
    .card {
      width: calc(32% - 40px);
      height: 480px;
    }
  }
}
</style>