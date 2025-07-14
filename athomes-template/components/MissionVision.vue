<template>
  <div
    class="w-full h-full container flex flex-row items-center justify-center font-[Poppins] relative"
  >
    <div
      class="w-full h-full flex flex-col justify-center gap-12 items-center py-24 z-10"
    >
      <div
        v-for="item in items"
        class="w-[760px] h-[180px] bg-white shadow-sm rounded-xl rounded-br-[90px] py-4 px-8"
      >
        <h1 class="text-2xl font-bold text-[#061DC5]">{{ item.label }}</h1>
        <p class="text-base py-4">{{ item.description }}</p>
      </div>
    </div>
    <div
      class="absolute w-[500px] h-[500px] bg-white rounded-full top-[60%] left-[60%] translate-[-50%]"
    />
    <div
      class="relative w-[500px] h-[500px] bg-white rounded-full ml-[-520px] overflow-hidden flex items-center justify-center"
    >
      <img
        src="../assets/images/buildings.jpg"
        class="w-full h-full absolute z-0"
      />
      <div class="w-full h-full absolute gradient opacity-70" />
      <h1 class="text-4xl font-medium z-10 text-white">
        Our <br />
        Mission & <br />
        Vision
      </h1>
    </div>
  </div>
</template>
<script setup lang="ts">
const items = ref([
  {
    label: "Mission",
    description:
      "As an independent Realty company aims to uplift the economic standard for every Filipino who is thriving and willing to share talents too to become a good citizen and uphold ethical manners abide by existing laws to its colleagues & community.",
  },
  {
    label: "Vision",
    description:
      "Dynamic realty company to envision as the leading real estate group in the Philippines by giving good example of service, sales armed, and integrity in the society.",
  },
]);
</script>

<style scoped>
.mission-vision {
  background: url("../assets/images/buildings.jpg") no-repeat center center
    fixed;
  background-size: contain;
  background-size: 100%;
}

.gradient {
  background-image: linear-gradient(
    to bottom right,
    #041dc2 0%,
    #2b3493 60%,
    #06a3e8 100%
  );
}
</style>
