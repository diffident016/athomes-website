<template>
  <div
    class="relative w-full py-16 flex flex-row items-center justify-center overflow-hidden px-4"
  >
    <div
      class="md:w-[220px] md:h-[220px] w-[150px] h-[150px] bg-[#2549D3] rounded-full flex items-center justify-center relative"
    >
      <h1 class="text-white font-[Poppins] md:text-3xl text-xl font-medium">
        Our <br />
        Partners
      </h1>
      <div
        class="absolute md:w-[220px] md:h-[220px] w-[150px] h-[150px] bg-white right-[-80px] rounded-full z-[-100]"
      />
    </div>
    <div class="md:w-[880px] w-[220px] flex items-center">
      <div
        class="conveyor-wrapper absolute"
        @mouseenter="isPaused = true"
        @mouseleave="isPaused = false"
      >
        <div class="conveyor-track" :class="{ paused: isPaused }">
          <!-- Original strip -->
          <div class="conveyor-strip">
            <img
              v-for="(logo, index) in logos"
              :key="index"
              :src="`https://res.cloudinary.com/dvtex4guw/image/upload/v1750489781/athomes/${logo}`"
              class="logo"
            />
          </div>
          <!-- Duplicate strip for seamless loop -->
          <div class="conveyor-strip" aria-hidden="true">
            <img
              v-for="(logo, index) in logos"
              :key="'dup-' + index"
              :src="`https://res.cloudinary.com/dvtex4guw/image/upload/v1750489781/athomes/${logo}`"
              class="logo"
            />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script setup lang="ts">
import { ref } from "vue";

const isPaused = ref(false);

const logos = [
  "smrb1dg5hplz7jzfd6wz.png",
  "rbvpg58tvsystqyyyh6e.png",
  "khqhghdrfl8ys6wuhj61.png",
  "clrlulkj6cwrfrocttfx.png",
  "jsflr66gdvgnnqv49bbg.png",
  "bqds1uiwymogob04qh06.png",
  "a7l7wczyngznkbhnhkcv.png",
  "ifkg6hpkpt0u700uvjoz.png",
  "duyfsjqgpmo0z0zu92x2.png",
  "trlj3ulkfryhu6ikluvu.png",
  "dwbfdqhlviaxsof3dhpb.png",
  "ejz2usckgizha6fra5o1.png",
  "kohpvfdvkruzgs7ynemm.png",
  "kff08dswtj6y0dq7pr56.png",
  "qrnncm1apkucfdf8x2xy.png",
];
</script>

<style scoped>
.conveyor-wrapper {
  overflow: hidden;
  width: 100%;
  padding: 1rem 0;
}

.conveyor-track {
  display: flex;
  width: max-content;
  animation: scroll-linear 40s linear infinite;
}

.conveyor-track.paused {
  animation-play-state: paused;
}

.conveyor-strip {
  display: flex;
}

.logo {
  height: 60px;
  margin: 0 2rem;
  flex-shrink: 0;
}

@keyframes scroll-linear {
  0% {
    transform: translateX(0);
  }
  100% {
    transform: translateX(-50%);
  }
}
</style>
