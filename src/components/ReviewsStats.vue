<script setup>
import { useReviewsStore } from "../stores/reviews.js";

const store = useReviewsStore();
</script>

<template>
  <div class="flex justify-between items-center">
    <h4 class="text-[18px] font-semibold text-white">
      {{ store.reviewsCount ? store.reviewsCount : 'No' }}
      Reviews</h4>
    <h4 class="text-[18px] font-semibold text-white">
      Avarage Rating: {{ isNaN(store.averageRating) ? 0 : store.averageRating }}
    </h4>
  </div>
</template>
