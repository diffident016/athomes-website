<template>
  <div class="w-full h-45 flex items-center justify-center mt-18 px-4">
    <div
      class="md:hidden w-full h-16 flex items-center justify-center bg-white rounded-lg"
    >
      <div
        :class="`${
          !mouseOn && 'opacity-100'
        } opacity-0 flex flex-row items-center w-full h-full px-4 transition-opacity duration-500 ease-in-out`"
      >
        <div class="w-full flex flex-col px-2">
          <!-- <div class="flex flex-row items-center gap-1 text-[#2549D3]">
            Search athomes
            <Icon size="18" name="lucide:chevron-down"></Icon>
          </div> -->
          <div class="h-7 border-b border-black/40">
            <input
              type="text"
              placeholder="Search for Agent or Property"
              class="w-full bg-transparent outline-none text-base text-black/40"
            />
          </div>
        </div>
        <div class="w-1/4 flex items-center justify-end">
          <button
            class="bg-[#2549D3] text-white px-4 py-2 rounded-lg hover:bg-[#1f3bb0] transition duration-300 cursor-pointer"
          >
            Search
          </button>
        </div>
      </div>
    </div>
    <div
      class="hidden md:flex w-full h-full container flex-row font-[Poppins] justify-center items-center md:max-w-[1000px] ml-12 relative"
    >
      <div
        :class="`flex flex-row z-10 items-center transition-all duration-500 ease-in-out absolute left-0 bottom-0 top-0 transform -translate-x-1/4`"
      >
        <SearchSwap
          search="agent"
          margin-one="mr-[-4.5rem]"
          margin-two="ml-[-2.5rem]"
          :mouse-on="mouseOn"
          :search-on="searchOn"
          @on-mouse-hover="(type) => (mouseOn = type)"
          @toggle-swap="(type) => (searchOn = type)"
        />
        <SearchSwap
          search="property"
          margin-one="ml-[-3.5rem]"
          margin-two="ml-[-9.5rem]"
          :mouse-on="mouseOn"
          :search-on="searchOn"
          @on-mouse-hover="(type) => (mouseOn = type)"
          @toggle-swap="(type) => (searchOn = type)"
        />
        <!-- <div
          @mouseleave="mouseOn = null"
          @mouseover="searchOn != 'property' && onMouseHover('property')"
          :class="`${
            searchOn == 'property'
              ? `w-38 h-38 bg-[#2549D3] z-10  ${
                  mouseOn != null && mouseOn != 'property' ? 'z-[-10]' : 'z-10'
                } ml-[-3.5rem]`
              : `w-32 h-32 bg-white ${
                  mouseOn == 'property' && 'scale-120'
                } ml-[-9.5rem]`
          }  rounded-full transition-all  duration-500 ease-in-out flex items-center justify-center shadow-lg cursor-pointer select-none`"
          @click="toggleSwap('property')"
        >
          <div
            :class="`${
              searchOn != 'property' && 'invert-40'
            } flex flex-col items-center`"
          >
            <img class="w-16 h-16" src="../assets/images/home_icon.png" />
            <h1>Home</h1>
          </div>
        </div> -->
      </div>
      <div
        class="bg-white w-full h-[100px] rounded-xl flex flex-row items-center text-black/50 pl-38 relative"
      >
        <h1
          class="absolute transition-all duration-500 ease-in text-xl"
          v-if="mouseOn"
        >
          {{
            mouseOn == "property" ? "Looking for a Home?" : "Looking for Agent?"
          }}
        </h1>
        <div
          v-if="searchOn == 'property'"
          :class="`${
            !mouseOn && 'opacity-100'
          } opacity-0 flex flex-row items-center w-full h-full px-8 transition-opacity duration-500 ease-in-out`"
        >
          <div class="w-1/3 flex flex-col px-4">
            <div
              @click="toggleLocation = !toggleLocation"
              class="flex flex-row items-center gap-1 text-[#2549D3] cursor-pointer select-none"
            >
              Location
              <Icon
                size="18"
                :name="`lucide:chevron-${toggleLocation ? 'up' : 'down'}`"
              ></Icon>
            </div>
            <div class="relative h-7 border-b border-black/40">
              <p
                class="text-base cursor-pointer"
                @click="toggleLocation = true"
              >
                {{ selectedLocation }}
              </p>
              <div
                v-if="toggleLocation"
                class="absolute flex flex-col w-full bg-white rounded-lg shadow-lg mt-2 z-10 p-2"
              >
                <div
                  v-for="location in locations"
                  :key="location"
                  class="px-2 py-1 hover:bg-gray-100 cursor-pointer"
                  @click="
                    toggleLocation = false;
                    selectedLocation = location;
                  "
                >
                  {{ location }}
                </div>
              </div>
            </div>
          </div>
          <div class="w-1/3 flex flex-col px-4">
            <div
              class="flex flex-row items-center gap-1 text-[#2549D3] cursor-pointer select-none"
              @click="togglePropertyType = !togglePropertyType"
            >
              Property Type
              <Icon
                size="18"
                :name="`lucide:chevron-${togglePropertyType ? 'up' : 'down'}`"
              ></Icon>
            </div>
            <div
              class="relative h-7 border-b border-black/40 flex flex-row items-end"
            >
              <p
                class="text-base cursor-pointer"
                @click="togglePropertyType = true"
              >
                {{ selectedPropertyType }}
              </p>
              <div
                v-if="togglePropertyType"
                class="absolute top-5 flex flex-col w-full bg-white rounded-lg shadow-lg mt-2 z-10 p-2"
              >
                <div
                  v-for="type in propertyTypes"
                  :key="type"
                  class="px-2 py-1 hover:bg-gray-100 cursor-pointer"
                  @click="
                    togglePropertyType = false;
                    selectedPropertyType = type;
                  "
                >
                  {{ type }}
                </div>
              </div>
            </div>
          </div>
          <div class="w-1/3 flex flex-col px-4">
            <div class="flex flex-row items-center gap-1 text-[#2549D3]">
              Maximum Price
              <Icon size="18" name="lucide:chevron-down"></Icon>
            </div>
            <div class="h-7 border-b border-black/40">
              <input
                type="text"
                placeholder="P 1,000,000"
                class="w-full bg-transparent outline-none text-base"
              />
            </div>
          </div>
          <div class="w-1/4 flex items-center justify-end">
            <button
              class="bg-[#2549D3] text-white px-4 py-2 rounded-lg hover:bg-[#1f3bb0] transition duration-300 cursor-pointer"
            >
              Search
            </button>
          </div>
        </div>
        <div
          v-else
          :class="`${
            !mouseOn && 'opacity-100'
          } opacity-0 flex flex-row items-center w-full h-full px-8 transition-opacity duration-500 ease-in-out`"
        >
          <div class="w-full flex flex-col px-4">
            <div class="flex flex-row items-center gap-1 text-[#2549D3]">
              Search for Agent
              <Icon size="18" name="lucide:chevron-down"></Icon>
            </div>
            <div class="h-7 border-b border-black/40">
              <input
                type="text"
                placeholder="Search by Name or Agency"
                class="w-full bg-transparent outline-none text-base"
              />
            </div>
          </div>
          <div class="w-1/4 flex items-center justify-end">
            <button
              class="bg-[#2549D3] text-white px-4 py-2 rounded-lg hover:bg-[#1f3bb0] transition duration-300 cursor-pointer"
            >
              Search
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
const searchOn = ref<"property" | "agent">("property");
const mouseOn = ref<"property" | "agent" | null>(null);

const locations = ref(["Cagayan de Oro City"]);
const propertyTypes = ref(["House and Lot", "Lot Only", "Commercial Property"]);

const toggleLocation = ref(false);
const togglePropertyType = ref(false);

const selectedLocation = ref("Cagayan de Oro City");
const selectedPropertyType = ref("House and Lot");
</script>
<style scoped></style>
