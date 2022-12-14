<script setup>
import { ref, computed } from "vue";

import Header from "./components/Header.vue";
import Carousel from "./components/Carousel.vue";
import Heading from "./components/Heading.vue";
import Controls from "./components/Controls.vue";

const slides = [
  {
    image: "image-hero-1.jpg",
    title: "Discover innovative ways to decorate",
    description:
      "We provide unmatched quality, comfort, and style for property owners across the country.  Our experts combine form and function in bringing your vision to life. Create a room in your own style with our collection and make your property a reflection of you and what you love.  ",
  },
  {
    image: "image-hero-2.jpg",
    title: "We are available all across the globe",
    description:
      "With stores all over the world, it's easy for you to find furniture for your home or place of business.  Locally, we’re in most major cities throughout the country. Find the branch nearest you using our store locator. Any questions? Don't hesitate to contact us today.",
  },
  {
    image: "image-hero-3.jpg",
    title: "Manufactured with the best materials",
    description:
      "Our modern furniture store provide a high level of quality. Our company has invested in advanced technology to ensure that every product is made as perfect and as consistent as possible. With three decades of experience in this industry, we understand what customers want for their home and office.",
  },
];
const index = ref(0);
const slide = computed(() => slides[index.value]);

function previousSlide() {
  index.value = (index.value - 1 + slides.length) % slides.length;
}

function nextSlide() {
  index.value = (index.value + 1) % slides.length;
}
</script>

<template>
  <main class="md:primary-grid | grid grid-cols-1 h-screen">
    <!-- First row -->
    <div class="relative md:row-span-2 md:col-span-2 md:h-auto h-[22.5rem]">
      <Header></Header>
      <Carousel :image="slide.image"></Carousel>
      <div class="md:hidden absolute bottom-0 right-0">
        <Controls :handle-previous="previousSlide" :handle-next="nextSlide" :small="true"></Controls>
      </div>
    </div>

    <Heading :title="slide.title" :description="slide.description"></Heading>

    <Controls class="md:flex hidden" :handle-previous="previousSlide" :handle-next="nextSlide"></Controls>

    <!-- To fill the remaining row space -->
    <div class="md:block hidden"></div>

    <!-- Second row -->
    <div>
      <img class="w-full h-full object-cover" src="/image-about-dark.jpg" alt="" />
    </div>

    <section class="md:col-span-2 md:pt-16 md:pb-0 py-12 md:px-12 px-8">
      <h2 class="mb-2 uppercase tracking-[0.3em] md:text-lg text-normal font-bold text-black">About our furniture</h2>
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
  </main>
</template>
