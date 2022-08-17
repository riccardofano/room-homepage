<script setup>
const { handlePrevious, handleNext } = defineProps(["handlePrevious", "handleNext"]);
</script>

<template>
  <div class="flex">
    <button @click="handlePrevious()" class="button">
      <img src="../assets/icon-angle-left.svg" alt="Previous slide" />
    </button>
    <button @click="handleNext()" class="button">
      <img src="../assets/icon-angle-right.svg" alt="Next slide" />
    </button>
  </div>
</template>

<style scoped>
.button {
  @apply w-20 h-20 flex items-center justify-center bg-black hover:opacity-70 active:opacity-40;
}
</style>
