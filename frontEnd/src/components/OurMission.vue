<template>
  <section class="relative bg-blue-50 py-12 overflow-hidden">
    <!-- Wave Background -->
    <div
      class="absolute top-0 left-0 w-full h-full"
      style="
        background-image: url('/wave.svg');
        background-size: cover;
        background-position: center top;
        z-index: -1;
      "
      aria-hidden="true"
    ></div>

    <div class="w-full md:container mx-auto md:py-12">
      <h2
        class="text-3xl tracking-tighter font-bold text-orange mb-10 text-center relative"
      >
        Our Guiding Principles
      </h2>

      <div
        class="-full p-2 grid grid-cols-1 md:grid-cols-2 gap-8 justify-center items-center relative"
      >
        <!-- Mission -->
        <div
          class="px-6 col-span-2 py-10 text-center rounded-lg shadow-md hover:shadow-lg transition-shadow duration-300 bg-white hover:bg-orange-50 md:col-span-1"
        >
          <h3 class="text-xl font-semibold text-blue-600 tracking-tighter mb-2">
            Our Mission
          </h3>
          <p class="text-gray-700">
            {{ mission }}
          </p>
        </div>

        <!-- Vision -->
        <div
          class="bg-white col-span-2  py-10 px-6 rounded-lg text-center shadow-md transition-all duration-300 hover:shadow-lg hover:bg-orange-50 md:col-span-1"
        >
          <h3
            class="mb-2 text-xl font-semibold tracking-tighter text-green-600"
          >
            Our Vision
          </h3>
          <p class="text-gray-700">
            {{ vision }}
          </p>
        </div>

        <!-- Values -->
        <div class="col-span-2 px-6 py-12 md:py-20 rounded-lg bg-transparent">
  <h2 class="text-2xl font-bold text-orange-500 text-center tracking-wider">
    Inspire. Solve. Lead.
  </h2>

  <h1 class="text-4xl py-3 font-bold text-gray-800 text-center">
    Our Core Values
  </h1>

  <ul class="grid grid-cols-2 md:grid-cols-4 mx-auto pt-10 text-gray-700 gap-4">
    <li
      v-for="(value, index) in values"
      :key="index"
      class="w-48 h-48 bg-white p-4 rounded-full flex flex-col justify-center items-center text-xl hover:border-2 hover:border-orange-500 transition-all duration-300 ease-in-out hover:bg-orange-50"
    >
      {{ value.text }}
      <span class="text-orange-500">
        <img :src="value.img" :alt="value.alt" class="max-w-full h-auto" />
      </span>
    </li>
  </ul>
</div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const mission = ref(
  "To inspire students through innovative STEM education, empower them to solve real-world challenges, and equip them with the skills to lead in a technology-driven future."
);

const vision = ref(
  "To transform education globally by fostering a culture of creativity and leadership in STEM, where every student is inspired to innovate, solve problems, and lead in their fields."
);

import exce from '../assets/media/excellence.png';
import incl from '../assets/media/inclusivity.png';
import ino from '../assets/media/inovate.png';
import empo from '../assets/media/empowerment.png';

const values = ref([
  {
    text: "Excellence",
    img: exce,
  },
  {
    text: "Inclusivity",
    img: incl,
  },
  {
    text: "Innovation",
    img: ino,
  },
  {
    text: "Empowerment",
    img: empo,
  },
]);
</script>

<style scope>
.element:nth-child(even) {
  margin-bottom: -1.25rem;
}
</style>
