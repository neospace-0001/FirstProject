<script setup>
import TopNav from '@/components/TopNav.vue';
import HeroSection from '@/components/HeroSection.vue';
import OurMission from '@/components/OurMission.vue';

import NavBar from '../components/NavBar.vue';
import AboutUs from '../components/AboutUs.vue';
import Announcements from '../components/Announcements.vue';
import Footer from '../components/Footer.vue';
</script>

<template>
 <div>
  <TopNav class="hidden md:block" />
  <NavBar/>
  <HeroSection />
  <AboutUs/>
  <OurMission />
  <Announcements/>
  <Footer/>
 </div>
</template>
