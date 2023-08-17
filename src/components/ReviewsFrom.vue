<script setup>
import { ref, watch } from "vue";
import Card from "./shared/Card.vue";
import RatingSelect from "./RatingSelect.vue";
import { useReviewsStore } from "../stores/reviews.js";
import { storeToRefs } from "pinia";

const store = useReviewsStore();
const text = ref("");
const btnDisabled = ref(false);
const message = ref("");
const rating = ref(10);

const { editedContent } = storeToRefs(store);

watch(editedContent, (newData) => {
  if (newData.editable) {
    text.value = newData.item.text;
    rating.value = newData.item.rating;
  }
});

watch(text, (newVal) => {
  if (newVal.trim().length <= 10) {
    btnDisabled.value = true;
    message.value = "Text must be at least 10 characters!";
  } else {
    btnDisabled.value = false;
    message.value = "";
  }
});

const handleSubmit = () => {
  const newReview = {
    text: text.value,
    rating: rating.value,
  };
  if (!store.editedContent.editable) {
    store.addReviews(newReview);
  } else {
    store.updateReview({
      ...newReview,
      id: store.editedContent.item.id,
    });
  }
};
const setRating = (val) => {
  rating.value = val;
  console.log(val);
};
</script>

<template>
  <Card class="rounded-xl p-8 mb-5">
    <form @submit.prevent="handleSubmit">
      <h2 class="text-center text-2xl font-bold mb-5">
        How would you rate your service with us?
      </h2>
      <!-- Rating Component -->
      <RatingSelect :rating="rating" @setRating="setRating" />
      <div
        class="border-2 rounded-xl flex justify-between items-center p-4 mb-5"
      >
        <input
          class="outline-none w-full"
          type="text"
          placeholder="Write a review"
          v-model="text"
        />
        <button type="submit" class="bg-green-500 p-2 rounded-md text-white" :disabled="btnDisabled">Send</button>
      </div>
      <div v-if="message !== ''" class="text-red-500 text-center">
        {{ message }}
      </div>
    </form>
  </Card>
</template>
