<script setup>
const { handlePrevious, handleNext } = defineProps(["handlePrevious", "handleNext"]);
</script>

<template>
  <div class="flex">
    <button @click="handlePrevious()" class="w-20 h-20 bg-black flex items-center justify-center hover:opacity-70">
      <img src="../assets/icon-angle-left.svg" alt="Previous slide" />
    </button>
    <button @click="handleNext()" class="w-20 h-20 bg-black flex items-center justify-center hover:opacity-70">
      <img src="../assets/icon-angle-right.svg" alt="Next slide" />
    </button>
  </div>
</template>
