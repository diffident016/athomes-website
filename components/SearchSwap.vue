<template>
  <div
    @mouseleave="emits('onMouseHover', null)"
    @mouseover="searchOn != search && emits('onMouseHover', search)"
    :class="` ${
      searchOn == search
        ? `w-38 h-38 bg-[#2549D3] z-10 ${marginOne} ${
            mouseOn != null && mouseOn != search ? 'z-[-10]' : 'z-10'
          }`
        : `w-32 h-32 bg-white ${mouseOn == search && 'scale-120'} ${marginTwo}`
    } rounded-full transition-all duration-500 ease-in-out flex items-center justify-center shadow-lg select-none cursor-pointer`"
    @click="emits('toggleSwap', search)"
  >
    <div
      :class="`${
        searchOn != search && 'invert-40'
      } flex flex-col items-center `"
    >
      <img
        v-if="search == 'agent'"
        class="w-16 h-16"
        src="../assets/images/agent_icon.png"
      />
      <img v-else class="w-16 h-16" src="../assets/images/property_icon.png" />
      <h1 class="capitalize">{{ search }}</h1>
    </div>
  </div>
</template>
<script setup lang="ts">
const { mouseOn, searchOn } = defineProps<{
  search: "property" | "agent";
  searchOn: "property" | "agent";
  mouseOn: "property" | "agent" | null;
  marginOne: string;
  marginTwo: string;
}>();

const emits = defineEmits<{
  (e: "toggleSwap", type: "property" | "agent"): void;
  (e: "onMouseHover", type: "property" | "agent" | null): void;
}>();
</script>
