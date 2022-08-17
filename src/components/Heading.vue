<script setup>
const { title, description } = defineProps(["title", "description"]);
</script>

<template>
  <section class="md:col-span-2 md:pt-[7.5rem] md:pb-0 py-12 md:px-[6.25rem] px-8">
    <Transition name="slide" mode="out-in">
      <div :key="title">
        <h1 class="font-semibold md:leading-[2.75rem] md:text-5xl text-4xl tracking-tighter text-black">
          {{ title }}
        </h1>
        <p class="mt-6 mb-5 tracking-tight leading-snug">{{ description }}</p>
        <a class="flex items-center gap-5 text-black uppercase tracking-[0.7em] hover:opacity-40" href="#">
          Shop now
          <img src="../assets/icon-arrow.svg" alt="" />
        </a>
      </div>
    </Transition>
  </section>
</template>

<style scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.25s ease-out;
}

.slide-enter-from {
  opacity: 0;
  transform: translateX(30px);
}

.slide-leave-to {
  opacity: 0;
  transform: translateX(30px);
}
</style>
