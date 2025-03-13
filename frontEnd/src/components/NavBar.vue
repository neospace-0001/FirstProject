<template>
  <div>
    <div class="bg-white text-black p-4 container py-6">
      <div class="max-w-7xl mx-auto flex justify-between items-center">
        <!-- Logo -->
        <a href="#" class="text-xl font-bold">MyApp</a>

        <!-- Desktop Menu -->
        <ul class="hidden sm:flex space-x-6">
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Home</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Edtech</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Software</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Engineering</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Shop</a
            >
          </li>
          <li>
            <a
              href="#"
              class="hover:text-gray-200 hover:bg-orange hover:rounded-full hover:px-3 hover:py-2"
              >Contacts</a
            >
          </li>
        </ul>

        <!-- call to action button -->
        <router-link
          to=""
          class="relative inline-block overflow-hidden rounded-full z-10"
        >
          <button
            class="bg-orange px-4 py-2 text-white hover:text-black hover:bg-purple-300"
          >
            Talk to Us
          </button>
        </router-link>
        <!-- Mobile Menu Button -->
        <button
          class="md:hidden text-black focus:outline-none"
          @click="toggleMenu"
        >
          ☰
        </button>
      </div>
    </div>
    <!-- Mobile Menu -->
    <div v-if="isMenuOpen" class="md:hidden bg-orange p-4  my-2">
      <ul class="flex flex-col space-y-2 w-full">
        <li><a href="#" class="hover:bg-gray-200">Home</a></li>
        <li><a href="#" class="hover:text-gray-200">Edtech</a></li>
        <li><a href="#" class="hover:text-gray-200">Software</a></li>
        <li><a href="#" class="hover:text-gray-200">Engineering</a></li>
        <li><a href="#" class="hover:text-gray-200">Shop</a></li>
        <li><a href="#" class="hover:text-gray-200">Contacts</a></li>
        <hr>
        <div>
          <ul class="flex flex-col justify-start items-start">
            <li>
              <a href="#" class="hover:text-gray-200"
                > 9:00am - 6:00pm, Mon - Fri</a>
            </li>
            <li><a href="#" class="hover:text-gray-200">Nakuru, Kenya</a></li>
          </ul>
        </div>
      </ul>
    </div>
    <!-- <svg class="absolute bottom-0 left-0 w-full h- text-purple-700 transition-all duration-300 ease-in-out hover:text-purple-500" viewBox="0 0 1440 320" fill="currentColor">
    <path d="M0,96L48,112C96,128,192,160,288,170.7C384,181,480,171,576,149.3C672,128,768,96,864,85.3C960,75,1056,85,1152,122.7C1248,160,1344,224,1392,256L1440,288V0H0Z"></path>
  </svg> -->
  </div>
</template>

<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<style lang="scss" scoped></style>
