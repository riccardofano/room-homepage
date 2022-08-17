<script setup>
import { ref } from "vue";
const open = ref(false);
</script>

<template>
  <header
    class="py-12 md:px-16 px-8 flex gap-12 items-center md:justify-start justify-center text-white drop-shadow-md"
  >
    <p class="text-bold text-3xl leading-none">room</p>
    <Transition name="appear" mode="in-out">
      <div
        :key="open"
        class="md:static fixed inset-0 md:px-0 px-8 flex items-center justify-between"
        :class="open && 'bg-white'"
      >
        <button class="md:hidden flex items-center justify-items-center">
          <img
            @click="open = !open"
            class="object-center"
            :class="open && 'hidden'"
            src="../assets/icon-hamburger.svg"
            alt="Open menu"
          />
          <img
            @click="open = !open"
            class="object-center"
            :class="!open && 'hidden'"
            src="../assets/icon-close.svg"
            alt="Close menu"
          />
        </button>

        <nav class="md:block md:text-white text-black" :class="open ? 'block' : 'hidden'">
          <ul class="flex gap-4">
            <li class="bb"><a class="block" href="#">home</a></li>
            <li class="bb"><a class="block" href="#">shop</a></li>
            <li class="bb"><a class="block" href="#">about</a></li>
            <li class="bb"><a class="block" href="#">contact</a></li>
          </ul>
        </nav>
      </div>
    </Transition>
  </header>
</template>

<style scoped>
.bb {
  position: relative;
}
.bb::before {
  content: "";
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background-color: currentColor;

  transform: scaleX(0);
  transform-origin: center;
  transition: transform 100ms ease-out;
}
.bb:hover::before {
  transform: scaleX(1);
}

.appear-enter-active,
.appear-leave-active {
  transition: all 100ms ease-in-out;
  transform: translateY(0);
}

.appear-enter-from {
  transform: translateY(-100%);
}

.appear-leave-to {
  transform: translateY(-100%);
}
</style>
