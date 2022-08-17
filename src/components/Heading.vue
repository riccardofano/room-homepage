<script setup>
const { title, description } = defineProps(["title", "description"]);
</script>

<template>
  <section class="col-span-2 pt-28 px-20">
    <Transition name="slide" mode="out-in">
      <div :key="title">
        <h1 class="font-bold text-5xl text-black">{{ title }}</h1>
        <p class="my-6 leading-snug">{{ description }}</p>
        <a class="flex items-center gap-4 text-black uppercase tracking-[0.5em] hover:opacity-40" href="#">
          Shop now<img src="../assets/icon-arrow.svg" alt="" />
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
  transform: translateY(-30px);
}

.slide-leave-to {
  opacity: 0;
  transform: translateY(-30px);
}
</style>
