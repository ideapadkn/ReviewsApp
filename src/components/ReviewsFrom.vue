<script setup>
import { ref } from "vue";
import Card from "./shared/Card.vue";

const text = ref("");
const btnDisabled = ref(false);
const message = ref("");
</script>

<template>
  <Card class="rounded-xl p-8">
    <form class="rounded">
      <h2 class="text-center text-2xl font-bold mb-5">How would you rate your service with us?</h2>
      <!-- Rating Component -->
      <div class="border-2 rounded-xl flex justify-between items-center p-4 mb-5">
        <input class="outline-none w-full" type="text" placeholder="Write a review" v-model="text" />
        <button type="submit" class="" :disabled="btnDisabled">Send</button>
      </div>
      <div class="text-red-500 text-center">Text must be at least 10 characters!</div>
    </form>
  </Card>
</template>
