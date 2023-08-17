<script setup>
import ReviewsFrom from "../components/ReviewsFrom.vue";
import ReviewsList from "../components/ReviewsList.vue";
import ReviewsStats from "../components/ReviewsStats.vue";
</script>

<template>
  <div>
    <div class="container mx-auto">
      <!-- Reviews Form -->
      <ReviewsFrom />
      <!-- Reviews Stats -->
      <ReviewsStats />
      <!-- Reviews List -->
      <ReviewsList />
    </div>
  </div>
</template>
