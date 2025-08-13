<template>
  <nav
    id="navbar"
    class="w-full h-20 md:h-28 relative flex items-center justify-between z-100 font-[Poppins] px-4 md:px-16 bg-transparent"
  >
    <a
      href="/"
      class="flex flex-row items-center gap-3 md:gap-4 cursor-pointer"
    >
      <img
        src="../assets/images/athomes.png"
        class="w-10 h-10 md:w-14 md:h-14 object-contain drop-shadow-sm drop-shadow-white"
        alt="ATHOMES Logo"
      />
      <h1 class="text-white text-lg md:text-2xl">ATHOMESPH.COM</h1>
    </a>
    <!-- Hamburger Icon for Mobile -->
    <button
      class="lg:hidden flex flex-col justify-center items-center w-10 h-10"
      @click="isOpen = !isOpen"
      aria-label="Toggle navigation"
    >
      <span class="block w-6 h-0.5 bg-white mb-1"></span>
      <span class="block w-6 h-0.5 bg-white mb-1"></span>
      <span class="block w-6 h-0.5 bg-white"></span>
    </button>
    <!-- Desktop Menu -->
    <div class="hidden lg:flex flex-row gap-8 md:gap-12 items-center">
      <a
        v-for="items in narbarItems"
        @click="emits('scrollToSection', items.href)"
        class="text-white text-base md:text-lg font-medium hover:text-[#06A3E8] transition-colors duration-300 cursor-pointer"
        :key="items.label"
      >
        {{ items.label }}
      </a>
      <a
        href="https://www.athomesdashboard.com/"
        target="_blank"
        class="text-white text-sm md:text-base drop-shadow-sm drop-shadow-white/80 font-medium transition-colors duration-300 cursor-pointer bg-[#2549D3] px-3 py-1.5 md:px-4 md:py-2 rounded-lg hover:bg-[#1f3bb0]"
      >
        Agents
      </a>
    </div>
    <!-- Mobile Menu -->
    <transition name="fade">
      <div
        v-if="isOpen"
        class="fixed inset-0 bg-black bg-opacity-80 flex flex-col items-center justify-center gap-8 z-200 md:hidden"
      >
        <button
          class="absolute top-6 right-6 text-white text-3xl"
          @click="isOpen = false"
          aria-label="Close navigation"
        >
          &times;
        </button>
        <a
          v-for="items in narbarItems"
          @click="handleMobileNav(items.href)"
          class="text-white text-2xl font-medium hover:text-[#06A3E8] transition-colors duration-300 cursor-pointer"
          :key="items.label"
        >
          {{ items.label }}
        </a>
        <a
          href="https://www.athomesdashboard.com/"
          class="text-white text-xl drop-shadow-sm drop-shadow-white/80 font-medium transition-colors duration-300 cursor-pointer bg-[#2549D3] px-6 py-3 rounded-lg hover:bg-[#1f3bb0]"
        >
          Agents
        </a>
      </div>
    </transition>
  </nav>
</template>

<script setup lang="ts">
import { ref } from "vue";

const emits = defineEmits(["scrollToSection"]);

const narbarItems = ref([
  { label: "Home", href: "home" },
  { label: "Mission & Vision", href: "mission-vision" },
  { label: "Partners", href: "partners" },
  { label: "About Us", href: "about-us" },
]);

const isOpen = ref(false);

function handleMobileNav(href: string) {
  emits("scrollToSection", href);
  isOpen.value = false;
}
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.3s;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
