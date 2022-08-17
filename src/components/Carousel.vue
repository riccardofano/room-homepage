<script setup>
const { image } = defineProps(["image"]);

function getImageUrl(image) {
  return new URL(`/desktop-${image}`, import.meta.url).href;
}
</script>

<template>
  <Transition name="appear" mode="in-out">
    <div :key="image" class="absolute inset-0">
      <img class="object-cover w-full h-full" :src="getImageUrl(image)" alt="" />
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
