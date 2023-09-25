<script>
export default {
  name: "RatingSelect",
  data() {
    return {
      selected: this.rating,
    };
  },
  props: {
    rating: {
      type: Number,
    },
  },
  watch: {
    selected(newVal) {
      this.$emit("setRating", newVal);
    },
    rating(newVal) {
      this.selected = newVal;
    },
  },
};
</script>

<template>
  <ul class="flex justify-between items-center mb-5">
    <li class="flex justify-center items-center" v-for="n in 10" :key="`rating-${n}`">
      <input class="relative flex justify-center items-center w-[25px] h-[25px]" type="radio" :id="`num${n}`"
        name="rating" :value="n" :checked="selected === n" v-model="selected" />
      <label class="absolute text-[14px]" :for="`num${n}`">
        {{ n }}
      </label>
    </li>
  </ul>
</template>
