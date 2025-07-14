<template>
  <div
    id="navbar"
    class="w-full h-28 relative flex flex-row items-center justify-between z-100 font-[Poppins] px-16"
  >
    <div
      class="flex flex-row items-center gap-4 drop-shadow-sm drop-shadow-white"
    >
      <img
        src="../assets/images/athomes.png"
        class="w-14 h-14 object-contain cursor-pointer"
        alt="ATHOMES Logo"
      />
      <!-- <h1 class="text-white text-2xl">ATHOMES</h1> -->
    </div>
    <div class="flex flex-row gap-12 items-center">
      <a
        v-for="items in narbarItems"
        href="{{ items.href }}"
        class="text-white text-lg font-medium hover:text-[#06A3E8] transition-colors duration-300 cursor-pointer"
        :key="items.label"
      >
        {{ items.label }}
      </a>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";

const narbarItems = ref([
  { label: "Home", href: "#" },
  { label: "Mission & Vision", href: "#mission-vision" },
  { label: "Partners", href: "#partners" },
  { label: "About Us", href: "#about-us" },
]);
</script>

<style scoped></style>
