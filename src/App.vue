<template>
  <div class=" h-screen flex flex-col items-center justify-center relative maindiv">
    <img src="/Cloud.svg" alt="Small Vector 1" class="cloud absolute z-10"/>
    <img src="/Birds.svg" alt="Small Vector 2" class="bird absolute z-10"/>
    <img src="/Layer2.png" alt="Spiral Vector" class="w-1/2 absolute z-0"/>
    <div class="flex space-x-2 z-9 mt-10">
      <div class="flex">
        <img src="/windowframe.png" alt="Window 1" class="relative w-56 h-56"/>
        <img src="/burj.png" alt="Window 1" class="imgs absolute w-56 h-56"/>
        <img src="/windowcover.png" alt="Window 1" class="absolute w-56 h-56 windowcover" ref="windowCover1"/>
      </div>
      <div class="flex">
        <img src="/windowframe.png" alt="Window 1" class="relative w-56 h-56"/>
        <img src="/taj.png" alt="Window 1" class="imgs absolute w-56 h-56"/>
        <img src="/windowcover.png" alt="Window 1" class="absolute w-56 h-56 windowcover" ref="windowCover2"/>
      </div>
      <div class="flex">
        <img src="/windowframe.png" alt="Window 1" class="relative w-56 h-56"/>
        <img src="/eifel.png" alt="Window 1" class="imgs absolute w-56 h-56"/>
        <img src="/windowcover.png" alt="Window 1" class="absolute w-56 h-56 windowcover" ref="windowCover3"/>
      </div>
    </div>
    <div>
      <p class="font-sans font-medium text-center">
        Attention Passengers: <br>
        <span class="text-blue-700 font-semibold">Your journey is about to begin.</span> <br>
        Please ensure your seatbelts are fastened and your <br> window shades are down
      </p>
    </div>
  </div>
  <Header/>
  <div class="font-sans banner h-screen w-screen bg-cover bg-no-repeat relative">
    <div class="text-white absolute bottom-16 left-32">
      <p class="text-5xl font-bold">Mastering Your <br> Journey</p>
      <div class="text-gray-300">
        <p>Let us help you explore the world's wonders in a way that</p><br>
        <p>speaks to your heart. Your perfect journey starts here!</p>
        <p class="text-white pt-28"><b>Popular Place :</b> Bali, Istanbul, Rome, Paris.</p>
      </div>
    </div>
  </div>
  <div class=" font-sans banner2 h-screen w-screen bg-cover bg-no-repeat relative space-y-9">
    <p class="banner2head text-center pt-12 text-3xl font-bold line-clamp-2">Explore new worlds with <br>
      exotic natural scenexlry</p>
    <p class="text-center text-gray-400 font-medium">Explore the world with what you love beautiful natural beauty.</p>
    <div class="flex w-full justify-center gap-8">
      <div class="cards shadow-lg w-60 h-60 bg-contain bg-no-repeat hover:scale-105 transition-all"></div>
      <div class="cards shadow-lg w-60 h-60 bg-contain bg-no-repeat hover:scale-105 transition-all relative">
        <p class="text-blue-700 font-bold absolute bottom-3 left-4">Bali, Indonesia</p>
      </div>
      <div class="cards shadow-lg w-60 h-60 bg-contain bg-no-repeat hover:scale-105 transition-all"></div>
    </div>
  </div>
  <footer class="font-sans bg-black w-full h-16 flex justify-center items-center">
    <p class="text-center text-white text-sm">Copyright © All rights reserved</p>
  </footer>
</template>

<script setup>
import { onMounted, ref, onUnmounted } from 'vue';
import Header from './components/Header.vue';

const windowCover1 = ref(null);
const windowCover2 = ref(null);
const windowCover3 = ref(null);

let scrollCount = 0;
const scrollIncrement = 20;

const handleScroll = () => {
  scrollCount++;
  const scrollValue = (scrollCount * scrollIncrement) / 1000;
  document.documentElement.style.setProperty('--scroll', scrollValue);
};

onMounted(() => {
  window.addEventListener('scroll', handleScroll);
});

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll);
});
</script>

<style scoped>
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
  overflow-x: hidden;
  height: 200vh;
  background-color: #ffffff;
}

.maindiv {
  position: relative;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;
  z-index: -30;
}

.windowcover {
  animation: slideIn 1s var(--scroll) both;
  z-index: -20;
}

@keyframes slideIn {
  from {
    transform: translateY(0%);
  }
  to {
    transform: translateY(-50%);
  }
}

.windowframe {
  z-index: -10;
}

.imgs {
  z-index: -25;
}
</style>
