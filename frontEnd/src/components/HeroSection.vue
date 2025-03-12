<template>
  <div class="carousel-container">
    <!-- Main carousel display -->
    <div class="carousel-wrapper">
      <div class="carousel-content" 
     :style="{ 
       transform: isInitialLoad 
         ? 'translateX(-100%)' 
         : `translateX(-${currentIndex * 100}%)`
     }">
        <div 
          v-for="(item, index) in carouselItems" 
          :key="index" 
          class="carousel-item"
        >
          <img :src="item.image" :alt="item.alt" class="carousel-image">
          <div class="carousel-caption">
            <h3>{{ item.title }}</h3>
            <p>{{ item.description }}</p>
          </div>
        </div>
      </div>
      
      <!-- Navigation buttons -->
      <button @click="prevSlide" class="carousel-control prev" aria-label="Previous slide">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chevron-left"><path d="m15 18-6-6 6-6"/></svg>
      </button>
      <button @click="nextSlide" class="carousel-control next" aria-label="Next slide">
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-chevron-right"><path d="m9 18 6-6-6-6"/></svg>
      </button>
    </div>
    
    <!-- Indicators -->
    <div class="carousel-indicators">
      <button 
        v-for="(_, index) in carouselItems" 
        :key="index"
        @click="goToSlide(index)"
        :class="['indicator', { active: currentIndex === index }]"
        :aria-label="`Go to slide ${index + 1}`"
      ></button>
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

const prevSlide = () => {
  currentIndex.value =
    (currentIndex.value - 1 + carouselItems.value.length) %
    carouselItems.value.length;
};

const goToSlide = (index) => {
  currentIndex.value = index;
};

onMounted(() => {
  // Short delay before starting the animation
  setTimeout(() => {
    isInitialLoad.value = false;
  }, 100);
  
  // Start the auto-rotation after the initial animation
  setTimeout(() => {
    intervalId = setInterval(nextSlide, 3000);
  }, 1000);
});

onUnmounted(() => {
  clearInterval(intervalId);
});
</script>

<style scoped>
.carousel-container {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  position: relative;
  overflow: hidden;
}

.carousel-wrapper {
  position: relative;
  overflow: hidden;
  border-radius: 8px;
}

.carousel-content {
  display: flex;
  transition: transform 0.8s ease;
  height: 400px;
}

.carousel-item {
  min-width: 100%;
  position: relative;
}

.carousel-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.carousel-caption {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0, 0, 0, 0.6);
  color: white;
  padding: 20px;
}

.carousel-caption h3 {
  margin: 0 0 10px 0;
  font-size: 1.5rem;
}

.carousel-control {
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  background: rgba(255, 255, 255, 0.5);
  border: none;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: background 0.3s;
}

.carousel-control:hover {
  background: rgba(255, 255, 255, 0.8);
}

.carousel-control.prev {
  left: 10px;
}

.carousel-control.next {
  right: 10px;
}

.carousel-indicators {
  display: flex;
  justify-content: center;
  margin-top: 10px;
  gap: 8px;
}

.indicator {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background: #ccc;
  border: none;
  cursor: pointer;
  transition: background 0.3s;
}

.indicator.active {
  background: #333;
}

@media (max-width: 768px) {
  .carousel-content {
    height: 300px;
  }
  
  .carousel-caption {
    padding: 10px;
  }
  
  .carousel-caption h3 {
    font-size: 1.2rem;
  }
}
</style>