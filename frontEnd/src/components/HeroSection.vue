<template>
  <div class="w-full bg-orange-50 relative overflow-hidden">
    <!-- Main carousel display -->
    <div class="overflow-hidden relative">
      <div
        class="relative h-[50vh] md:h-[70vh]" 
      >
        <div
          v-for="(item, index) in carouselItems"
          :key="index"
          class="absolute top-0 left-0 w-full h-full transition-opacity duration-800 ease-in-out"
          :class="{ 'opacity-100': currentIndex === index, 'opacity-0': currentIndex !== index }"
          :aria-hidden="currentIndex !== index"
        >
          <div
            class="w-full h-full bg-cover  bg-center"
            :style="{ backgroundImage: `url(${item.image})` }"
            :aria-label="item.alt"
            role="img"
          > 
          <!-- div for small screens -->
          <div
            class=" absolute top-0 bottom-0 left-0 right-0 px-4 text-center md:hidden bg-black/80 text-orange flex flex-col justify-end items-center pb-16"
          >
            <h3 class="text-xl mb-2 font-semibold">{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>

          <!-- Div for big screen -->
          <div
            class="hidden absolute bottom-32 rounded-full bg-white right-32 w-120 h-120 border-5 shadow-2xl border-orange  text-orange p-5 md:flex flex-col justify-center items-center"
          >
            <h3 class="text-xl mb-2 font-semibold">{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
          </div>
        </div>
      </div>

      <!-- Navigation buttons -->
      <!-- <button
        @click="prevSlide"
        class="absolute top-1/2 transform -translate-y-1/2 bg-orange hover:bg-orange/80 w-10 h-10 rounded-full flex items-center justify-center cursor-pointer transition-colors duration-300 left-2"
        aria-label="Previous slide"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="lucide lucide-chevron-left"
        >
          <path d="m15 18-6-6 6-6" />
        </svg>
      </button>
      <button
        @click="nextSlide"
        class="absolute top-1/2 transform -translate-y-1/2  bg-orange hover:bg-orange/80 w-10 h-10 rounded-full flex items-center justify-center cursor-pointer transition-colors duration-300 right-2"
        aria-label="Next slide"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="24"
          height="24"
          viewBox="0 0 24 24"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
          class="lucide lucide-chevron-right"
        >
          <path d="m9 18 6-6-6-6" />
        </svg>
      </button> -->
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const carouselItems = ref([
  {
    image: "../src/assets/media/hero.jpg",
    alt: "Image 1",
    title: "EdTech",
    description:
      "Item 1 Description: This is some example text for the first carousel item.",
  },
  {
    image: "../src/assets/media/hero1.jpg",
    alt: "Image 2",
    title: "Software",
    description:
      "Item 2 Description: This is some example text for the second carousel item.",
  },
  {
    image: "../src/assets/media/hero2.jpg",
    alt: "Image 3",
    title: "engineering",
    description:
      "Item 3 Description: This is some example text for the third carousel item.",
  },

]);

const currentIndex = ref(0);
const isInitialLoad = ref(true);
let intervalId;

const nextSlide = () => {
  currentIndex.value = (currentIndex.value + 1) % carouselItems.value.length;
};
// const prevSlide = () => {
//   currentIndex.value =
//     (currentIndex.value - 1 + carouselItems.value.length) %
//     carouselItems.value.length;
// };


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

