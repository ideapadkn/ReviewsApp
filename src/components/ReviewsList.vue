<script setup>
import ReviewsItem from "./ReviewsItem.vue";
import { useReviewsStore } from "../stores/reviews.js";

const store = useReviewsStore();
</script>

<template>
  <div>
    <p v-if="!store.reviewsContent || store.reviewsContent.length === 0" class="text-white mb-5">
      No Reviews Yet
    </p>
    <div v-else>
      <ReviewsItem v-for="(item, i) in store.reviewsContent" :key="i" :item="item" />
    </div>
  </div>
</template>
