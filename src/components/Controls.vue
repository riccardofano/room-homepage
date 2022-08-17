<script setup>
const { handlePrevious, handleNext, small } = defineProps(["handlePrevious", "handleNext", "small"]);
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
  @apply md:w-20 md:h-20 w-14 h-14 flex items-center justify-center bg-black hover:opacity-70 active:opacity-40;
}

.button > img {
  @apply scale-75 origin-center;
}
</style>
