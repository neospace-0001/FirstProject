<template>
  <div class="w-full bg-orange-50 relative overflow-hidden">
    <!-- Main carousel display -->
    <div class="overflow-hidden relative">
      <div class="relative h-[50vh] md:h-[70vh]">
        <div
          v-for="(item, index) in carouselItems"
          :key="index"
          class="absolute top-0 left-0 w-full h-full transition-opacity duration-800 ease-in-out"
          :class="{
            'opacity-100': currentIndex === index,
            'opacity-0': currentIndex !== index,
          }"
          :aria-hidden="currentIndex !== index"
        >
          <div
            class="w-full h-full bg-cover bg-center"
            :style="{ backgroundImage: `url(${item.image})` }"
            :aria-label="item.alt"
            role="img"
          >
            <!-- div for small screens -->
            <div
              class="absolute top-0 bottom-0 left-0 right-0 px-4 text-center md:hidden bg-black/80 text-orange flex flex-col justify-end items-center pb-16"
            >
              <h3 class="text-xl mb-2 font-semibold">{{ item.title }}</h3>
              <p>{{ item.description }}</p>
            </div>

            <!-- Div for big screen -->
            <div
              class="hidden absolute bottom-32 rounded-full bg-black/80 right-32 w-120 h-120 border-5 shadow-2xl border-orange text-orange p-5 md:flex flex-col justify-center items-center"
            >
              <h3 class="text-2xl mb-2 capitalize font-semibold pb-6">
                {{ item.title }}
              </h3>
              <p class="text-xl text-center tracking-tighter">
                {{ item.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

import hero from "../assets/media/hero.jpg";
import hero1 from "../assets/media/hero1.jpg";
import hero2 from "../assets/media/hero2.jpg";

const carouselItems = ref([
  {
    image: hero,
    alt: "Image 1",
    title: "Education Tech",
    description: "This is some example text for the first carousel item.",
  },
  {
    image: hero1,
    alt: "Image 2",
    title: "Software",
    description: "This is some example text for the second carousel item.",
  },
  {
    image: hero2,
    alt: "Image 3",
    title: "engineering",
    description: "This is some example text for the third carousel item.",
  },
]);

const currentIndex = ref(0);
const isInitialLoad = ref(true);
let intervalId;

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % carouselItems.value.length;
};

onMounted(() => {
  // Short delay before starting the animation
  setTimeout(() => {
    isInitialLoad.value = false;
  }, 100);

  // Start the auto-rotation after the initial animation
  setTimeout(() => {
    intervalId = setInterval(nextSlide, 5000);
  }, 5000);
});

onUnmounted(() => {
  clearInterval(intervalId);
});
</script>

<style scoped>
@keyframes rotateScale {
  0% {
    transform: rotate(0deg) scale(1);
  }
  50% {
    transform: rotate(180deg) scale(1.2);
  }
  100% {
    transform: rotate(360deg) scale(1);
  }
}
</style>
