<template>
  <div
    class="w-full h-full flex justify-center items-center container font-[Poppins]"
  >
    <div
      class="justify-start items-center md:max-w-[1100px] flex relative w-full"
    >
      <div
        class="w-full h-full flex flex-col justify-center md:items-start items-center gap-12 py-24 z-10 relative"
      >
        <div
          v-for="(item, i) in items"
          :class="`md:w-[760px] md:h-[180px] w-[350px] bg-white shadow-sm rounded-xl ${
            i == 1 ? 'rounded-tr-[90px]' : 'rounded-br-[90px]'
          } py-4 px-8 z-10`"
        >
          <h1 class="text-2xl font-bold text-[#061DC5]">{{ item.label }}</h1>
          <p class="md:text-base text-xs py-4">{{ item.description }}</p>
        </div>
      </div>
      <div
        class="absolute md:right-0 right-4 md:w-[500px] md:h-[500px] w-[400px] h-[400px] bg-white rounded-full overflow-hidden flex items-center justify-center ml-[-9%]"
      >
        <img
          src="../assets/images/buildings.jpg"
          class="w-full h-full absolute z-0"
        />
        <div class="w-full h-full absolute gradient opacity-70" />
        <h1 class="hidden md:block text-4xl font-medium z-10 text-white">
          Our <br />
          Mission & <br />
          Vision
        </h1>
      </div>
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
