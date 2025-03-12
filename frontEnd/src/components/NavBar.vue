<template>

<nav class="bg-orange-600 p-4">
    <div class="max-w-7xl mx-auto flex justify-between items-center">
      <!-- Logo -->
      <a href="#" class="text-white text-xl font-bold">MyApp</a>

      <!-- Desktop Menu -->
      <ul class="hidden md:flex space-x-6 text-white">
        <li><a href="#" class="hover:text-gray-200">Home</a></li>
        <li><a href="#" class="hover:text-gray-200">Edtech</a></li>
        <li><a href="#" class="hover:text-gray-200">Software</a></li>
        <li><a href="#" class="hover:text-gray-200">Engineering</a></li>
        <li><a href="#" class="hover:text-gray-200">Shop</a></li>
        <li><a href="#" class="hover:text-gray-200">Contacts</a></li>
      </ul>

      <!-- Mobile Menu Button -->
      <button
        class="md:hidden text-white focus:outline-none"
        @click="toggleMenu"
      >
        ☰
      </button>
    </div>

    <!-- Mobile Menu -->
    <div v-if="isMenuOpen" class="md:hidden bg-blue-700 p-4">
      <ul class="flex flex-col space-y-4 text-white">
        <li><a href="#" class="hover:text-gray-200">Home</a></li>
        <li><a href="#" class="hover:text-gray-200">Edtech</a></li>
        <li><a href="#" class="hover:text-gray-200">Software</a></li>
        <li><a href="#" class="hover:text-gray-200">Engineering</a></li>
        <li><a href="#" class="hover:text-gray-200">Shop</a></li>
        <li><a href="#" class="hover:text-gray-200">Contacts</a></li>
      </ul>
    </div>
  </nav>
</template>

<script setup>
import { ref } from "vue";

const isMenuOpen = ref(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<style lang="scss" scoped></style>
