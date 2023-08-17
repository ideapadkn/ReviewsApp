<script setup>
import Card from "./shared/Card.vue";
</script>

<template>
  <Card class="relative rounded-xl p-4">
    <div class="absolute top-[0] right-2">
      <button class="">X</button>
      <button class="ml-3">E</button>
    </div>
    <div
      class="absolute top-[-10px] left-[-10px] w-[30px] h-[30px] bg-green-500 rounded-full flex justify-center items-center text-2xl text-white"
    >
      <!-- {{ it }} -->
      5
    </div>
    <div class="flex justify-center items-center">
      Lorem ipsum dolor, sit amet consectetur adipisicing elit.
    </div>
  </Card>
</template>
