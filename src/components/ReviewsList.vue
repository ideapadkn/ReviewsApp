<script setup>
import ReviewsItem from "./ReviewsItem.vue";
import { useReviewsStore } from "../stores/reviews.js";

const store = useReviewsStore();
</script>

<template>
  <div>
    <p class="text-white mb-5">No Reviews Yet</p>
    <div>
      <ReviewsItem
        v-for="(item, i) in store.reviewsContent"
        :key="i"
        :item="item"
      />
    </div>
  </div>
</template>
