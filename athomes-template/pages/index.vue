<template>
  <div class="w-full h-full flex flex-col">
    <div id="navbar-container" class="absolute top-0 z-[1000] w-full">
      <Navbar />
    </div>
    <div class="hero w-full h-screen flex items-center justify-center">
      <div class="gradient w-full h-full absolute opacity-60"></div>
      <div
        class="container w-full h-full flex flex-col items-center justify-center text-white z-100 mt-16"
      >
        <h1 class="font-medium font-[Poppins] text-8xl">ATHOMES</h1>
        <p class="font-[QwitcherGrypen] text-5xl">
          - where you truly feel at Home! -
        </p>
        <SearchBar />
      </div>
    </div>
    <MissionVision />
    <Partners />
    <AboutUs />
    <Footer />
  </div>
</template>

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
</style>
