<script setup>
const { image } = defineProps(["image"]);

function getImageUrl(image) {
  return new URL(`/desktop-${image}`, import.meta.url).href;
}
</script>

<template>
  <div class="absolute inset-0">
    <img class="object-cover w-full h-full" :src="getImageUrl(image)" alt="" />
  </div>
</template>
