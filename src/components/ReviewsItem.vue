<script setup>
import { defineProps } from "vue";
import Card from "./shared/Card.vue";
import { useReviewsStore } from "../stores/reviews.js";

const store = useReviewsStore();
defineProps({
  item: {
    type: Object,
  },
});
</script>

<template>
  <Card class="relative rounded-xl p-6 mb-5">
    <div class="absolute top-[0] right-2">
      <button class="" @click="store.editReview(item)">E</button>
      <button class="ml-3" @click="store.deleteReview(item)">X</button>
    </div>
    <div
      class="absolute top-[-10px] left-[-10px] w-[40px] h-[40px] bg-green-500 rounded-full flex justify-center items-center text-2xl text-white"
    >
      {{ item.rating }}
    </div>
    <div class="flex justify-center items-center">
      {{ item.text }}
    </div>
  </Card>
</template>
