<script setup>
const { image } = defineProps(["image"]);

function getImageUrl(image, size) {
  return new URL(`../assets/${size}-${image}`, import.meta.url).href;
}
console.log(image);
</script>

<template>
  <Transition name="appear" mode="in-out">
    <div :key="image" class="absolute inset-0 -z-10">
      <img class="md:hidden block object-cover w-full h-full" :src="getImageUrl(image, 'mobile')" alt="" />
      <img class="md:block hidden object-cover w-full h-full" :src="getImageUrl(image, 'desktop')" alt="" />
    </div>
  </Transition>
</template>

<style scoped>
.appear-enter-active,
.appear-leave-active {
  transition: all 0.25s ease-out;
}

.appear-enter-from {
  opacity: 0;
}

.appear-leave-to {
  opacity: 0;
}
</style>
