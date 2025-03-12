<template>
    <section class="relative py-12 overflow-hidden">
      <!-- Wave Background -->
      <div
        class="absolute top-0 left-0 w-full h-full"
        style="background-image: url('/wave.svg'); background-size: cover; background-position: center top; z-index: -1;"
        aria-hidden="true"
      ></div>
  
      <div class="container mx-auto ">
        <h2 class="text-3xl font-semibold text-orange mb-8 text-center relative">Our Guiding Principles</h2>
  
        <div class="grid grid-cols-1 md:grid-cols-3 gap-8 relative">
          <!-- Mission -->
          <div class="p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 bg-white">
            <h3 class="text-xl font-semibold text-blue-600 mb-2">Our Mission</h3>
            <p class="text-gray-700">
              {{ mission }}
            </p>
          </div>
  
          <!-- Vision -->
          <div class="p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 bg-white">
            <h3 class="text-xl font-semibold text-green-600 mb-2">Our Vision</h3>
            <p class="text-gray-700">
              {{ vision }}
            </p>
          </div>
  
          <!-- Values -->
          <div class="p-6 rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 bg-white">
            <h3 class="text-xl font-semibold text-purple-600 mb-2">Our Values</h3>
            <ul class="list-disc list-inside text-gray-700">
              <li v-for="(value, index) in values" :key="index">{{ value }}</li>
            </ul>
          </div>
        </div>
      </div>
    </section>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  
  const mission = ref(
    "To empower individuals and organizations to achieve their full potential through innovative solutions and unwavering support."
  );
  
  const vision = ref(
    "To be a global leader in providing transformative services that create lasting positive impact on communities and the world."
  );
  
  const values = ref([
    "Integrity: We uphold the highest ethical standards in all our actions.",
    "Innovation: We embrace creativity and continuous improvement.",
    "Collaboration: We work together to achieve shared goals.",
    "Excellence: We strive for the best in everything we do.",
    "Impact: We are committed to making a meaningful difference.",
  ]);
  </script>