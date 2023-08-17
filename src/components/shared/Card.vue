<script>
export default {
  name: "Card",
  props: {
    reverse: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<template>
  <div class="bg-[#fff] text-[#212121]" :class="{ reverse: reverse }">
    <slot />
  </div>
</template>

<style>
.card.reverse {
  background: #212121;
  color: #fff;
}
</style>
