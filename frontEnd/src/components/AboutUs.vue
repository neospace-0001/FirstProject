<template>
  <section class="py-14">
    <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex flex-col lg:flex-row items-center gap-16 py-5 md:py-0">
        <div class="w-full lg:w-1/2 space-y-8">
          <div class="space-y-4">
            <h2 class="text-4xl font-bold tracking-tight text-gray-900">
              Creating Digital Excellence Together
            </h2>
            <p class="text-xl text-purple-500 font-semibold">
              Empowering Businesses Through Innovation Since 2010
            </p>
            <div class="text-gray-600">
              <p>
                At the forefront of digital transformation, we are a team of
                forward-thinking experts committed to delivering innovative
                solutions that propel businesses forward. Our track record spans
                over a decade, during which we&#39;ve empowered countless
                organizations worldwide to achieve their digital ambitions.
              </p>
              <p>
                By seamlessly blending technical expertise with creative
                ingenuity, we craft solutions that not only address current
                needs but anticipate future challenges. Our commitment to
                excellence and collaborative approach ensures each project
                delivers exceptional value and fosters long-term partnerships.
              </p>
            </div>
          </div>
          <button
            class="inline-flex text-purple-500 items-center px-6 py-3 bg-white rounded-2xl border-2 border-purple-500 font-medium"
          >
            Start Your Journey <i class="fas fa-arrow-right ml-2"></i>
          </button>
        </div>
        <div
          class="relative w-1/2 mx-auto overflow-hidden rounded-lg shadow-xl"
        >
          <div
            class="flex transition-transform ease-in-out"
            :style="{
              transform: `translateX(-${currentIndex * 100}%)`,
              transition: 'transform 3s ease-in-out',
            }"
          >
            
            <img
              v-for="(image, index) in images"
              :key="index"
              :src="image"
              alt="Image"
              class="w-full h-90 object-cover"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

import bird from "../assets/bird.jpeg";
import girl from "../assets/girl.jpeg";
import chimp from "../assets/chimps.jpeg";

const images = ref([bird, girl, chimp]);

const currentIndex = ref(0);
</script>

<style lang="scss" scoped>
.transition-transform {
  display: flex;
  width: 300%;
}
</style>
