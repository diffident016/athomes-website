<template>
  <div class="w-full h-full flex flex-col">
    <div id="navbar-container" class="absolute top-0 z-[1000] w-full">
      <Navbar @scrollToSection="scrollToSection" />
    </div>
    <div
      id="home"
      class="hero w-full h-screen flex items-center justify-center"
    >
      <div class="gradient w-full h-full absolute opacity-60"></div>
      <div
        class="container w-full h-full flex flex-col items-center justify-center text-white z-100 mt-16"
      >
        <h1 class="font-medium font-[Poppins] md:text-8xl text-5xl">ATHOMES</h1>
        <p class="font-[QwitcherGrypen] md:text-5xl text-3xl">
          - where you truly feel at Home! -
        </p>
        <SearchBar />
      </div>
    </div>
    <MissionVision id="mission-vision" />
    <Partners id="partners" />
    <AboutUs id="about-us" />
    <Footer id="footer" />
  </div>
</template>

<script setup lang="ts">
const HEADER_OFFSET = 0;

function scrollToSection(sectionId: string) {
  //console.log("Scrolling to section:", sectionId);
  const section = document.getElementById(sectionId);
  if (!section) return;
  const y =
    section.getBoundingClientRect().top + window.scrollY - HEADER_OFFSET;
  window.scrollTo({ top: y, behavior: "smooth" });
}
</script>

<style>
.hero {
  background: url("https://res.cloudinary.com/dvtex4guw/image/upload/v1748584209/athomes/abstusldo3siy05bmsfp.jpg")
    no-repeat center center fixed;
  background-size: cover;
  background-size: 100% 100%;
}

.gradient {
  background-image: linear-gradient(
    to bottom right,
    #041dc2 0%,
    #2b3493 60%,
    #06a3e8 100%
  );
}

html {
  scroll-behavior: smooth;
}
</style>
