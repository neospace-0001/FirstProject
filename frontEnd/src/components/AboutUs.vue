<template>
  <!-- <div class="max-w-6xl mx-auto bg-gray-500">
    <div class="bg-white flex justify-around items-center">
      <div class="py-10 space-y-3">
        <h1 class="text-4xl tracking-wider uppercase">yellow</h1>
        <h2 class="text-2xl ">lorry</h2>
        <p class="">Have you ever seen such a view wijdb jvjndfvnhfvgbbvjfvjkfvjhfvbfffnf hfvjhhbhbvwuhf<br> jhjhfhbvbfhdbvfdbg jvfjhvjhfvdfbvfjdjhf  hfvhfdvfvhfdjvhf</p>
        <button class="px-3 py-2 rounded-full border-2 border-orange hover:bg-orange hover:text-white">call to us</button>
      </div>
      <div class="carousel">
        <button @click="prevImage" class="nav-btn">‹</button>
        <div class="image-container">
          <img
            :src="images[currentIndex]"
            alt="Carousel Image"
            class="carousel-image"
          />
        </div>
        <button @click="nextImage" class="nav-btn">›</button>
      </div>
    </div> -->
    <section class=" min-h-screen py-14 ">
        
        
        <div class="relative max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex flex-col lg:flex-row items-center gap-16">
                
                <div class="w-full lg:w-1/2 space-y-8">
                    <div class="space-y-4">
                        <h2 class="text-4xl font-bold tracking-tight text-gray-900">Creating Digital Excellence Together</h2>
                        <p class="text-xl text-purple-500 font-semibold">Empowering Businesses Through Innovation Since 2010</p>
                        <div class="prose prose-lg text-gray-600">
                            <p>At the forefront of digital transformation, we are a team of forward-thinking experts committed to delivering innovative solutions that propel businesses forward. Our track record spans over a decade, during which we&#39;ve empowered countless organizations worldwide to achieve their digital ambitions.</p>
                            <p>By seamlessly blending technical expertise with creative ingenuity, we craft solutions that not only address current needs but anticipate future challenges. Our commitment to excellence and collaborative approach ensures each project delivers exceptional value and fosters long-term partnerships.</p>
                        </div>
                    </div>
                    <button class="inline-flex text-purple-500 items-center px-6 py-3 bg-white rounded-2xl border-2 border-purple-500 font-medium ">Start Your Journey <i class="fas fa-arrow-right ml-2"></i></button>
                </div>
                <div class="w-full lg:w-1/2">
                    <div class=" h-[500px] rounded-lg shadow-xl">
                        
                            <ul class="glide__slides">
                                <li class="glide__slide">
                                    <img src="https://www.pexels.com/photo/photo-of-person-covered-with-brown-textile-906052/" alt="Image" class="w-full h-full object-cover"/>
                                </li>
                               
                            </ul>
                        
                    </div>
                </div>
                
            </div>
        </div>
    </section>
  <!-- </div> -->



</template>

<script setup>
// import { ref } from "vue";

// const images = ref([
  // "https://www.pexels.com/photo/photo-of-person-covered-with-brown-textile-906052/",
  // "https://www.pexels.com/photo/selective-focus-photography-of-a-red-rose-593655/",
  // "https://www.pexels.com/photo/close-up-photo-of-pink-and-yellow-silk-flower-39574/",
// ]);

// const currentIndex = ref(0);

// const nextImage = () => {
//   currentIndex.value = (currentIndex.value + 1) % images.value.length;
// };

// const prevImage = () => {
//   currentIndex.value =
//     (currentIndex.value - 1 + images.value.length) % images.value.length;
// };
</script>

<style lang="scss" scoped></style>
