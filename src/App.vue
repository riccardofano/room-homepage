<script setup>
import Header from "./components/Header.vue";
</script>

<template>
  <div class="md:primary-grid | grid h-screen">
    <!-- First row -->
    <div class="row-span-2 col-span-2 relative">
      <div class="absolute inset-0">
        <img class="object-cover w-full h-full" src="/desktop-image-hero-1.jpg" alt="" />
      </div>
      <Header />
    </div>

    <section class="col-span-2 pt-28 px-20">
      <h1 class="font-bold text-5xl text-black">Discover inovative ways to decorate</h1>
      <p class="my-6 leading-snug">
        We provide unmatched quality, comfort, and style for property owners across the country. Our experts combine
        form and function in bringing your vision to life. Create a room in your own style with our collection and make
        your property a reflection of you and what you love.
      </p>
      <a class="flex items-center gap-4 text-black uppercase tracking-[0.5em]" href="#"
        >Shop now<img src="./assets/icon-arrow.svg" alt=""
      /></a>
    </section>

    <div class="flex">
      <button class="w-20 h-20 bg-black flex items-center justify-center">
        <img src="./assets/icon-angle-left.svg" alt="Previous slide" />
      </button>
      <button class="w-20 h-20 bg-black flex items-center justify-center">
        <img src="./assets/icon-angle-right.svg" alt="Next slide" />
      </button>
    </div>

    <!-- To fill the remaining row space -->
    <div></div>

    <!-- Second row -->
    <div>
      <img class="w-full h-full object-cover" src="/image-about-dark.jpg" alt="" />
    </div>

    <section class="col-span-2 pt-16 px-12">
      <h2 class="mb-2 uppercase tracking-[0.3em] text-lg font-bold text-black">About our furniture</h2>
      <p class="tracking-tight leading-snug">
        Our multifunctional collection blends design and function to suit your individual taste. Make each room unique,
        or pick a cohesive theme that best express your interests and what inspires you. Find the furniture pieces you
        need, from traditional to contemporary styles or anything in between. Product specialists are available to help
        you create your dream space.
      </p>
    </section>

    <div>
      <img class="w-full h-full object-cover" src="/image-about-light.jpg" alt="" />
    </div>
  </div>
</template>
