<template>
  <div
    class="gradient w-full md:h-[450px] flex flex-col gap-10 font-[Poppins] text-white"
  >
    <div class="w-full bg-[#fafafa] h-[100px] rounded-bl-[100px]" />
    <div class="w-full h-full flex md:flex-row flex-col justify-center gap-24">
      <div class="flex flex-col items-center">
        <img
          src="../assets/images/athomes.png"
          class="w-26 object-contain cursor-pointer drop-shadow-sm drop-shadow-white py-4"
          alt="ATHOMES Logo"
        />
        <h1 class="font-medium text-3xl">ATHOMES Realty</h1>
        <p class="font-[QwitcherGrypen] text-4xl pt-2">
          Where you truly feel at Home!
        </p>
      </div>
      <div
        class="flex flex-row h-full w-full gap-8 md:w-[600px] md:px-0 px-8 md:justify-start justify-center"
      >
        <div class="w-full flex flex-col gap-4">
          <h1 class="text-lg font-bold">Get in Touch:</h1>
          <p class="font-thin text-sm">
            You may get in touch with <br />
            us through the contact <br />
            numbers below:
          </p>
          <div class="flex flex-col text-sm gap-1">
            <p class="font-medium flex flex-row items-center gap-1">
              <Icon size="14" name="lucide:phone" /> +63 912 345 6789
            </p>
            <p class="font-medium flex flex-row items-center gap-1">
              <Icon size="14" name="lucide:phone" /> +63 912 345 6789
            </p>
          </div>
          <div class="flex flex-col text-sm gap-1 w-full">
            <p class="font-bold flex flex-row items-center gap-2">
              Our Office:
            </p>
            <a
              class="font-medium flex flex-row items-center gap-2 w-full cursor-pointer"
              href="https://maps.app.goo.gl/QP7ApGPwicRRheB18"
              target="_blank"
            >
              <Icon size="20" name="lucide:map-pin" /> Door 12, KMV Building,
              Pabayo Street, <br />
              Cagayan de Oro City, 9000
            </a>
          </div>
        </div>
        <div class="w-full flex flex-col gap-4">
          <h1 class="text-lg font-bold">Follow Us:</h1>

          <div class="flex flex-col text-sm gap-2">
            <a
              class="font-medium flex flex-row items-center gap-1 cursor-pointer"
              href="https://www.fb.com/athomescdorecruitement"
              target="_blank"
            >
              <img
                class="invert"
                src="~/assets/images/circum_facebook.png"
                :width="30"
                :height="30"
              />
              Facebook
            </a>
            <a
              class="font-medium flex flex-row items-center gap-1 cursor-pointer"
            >
              <img
                class="invert"
                src="~/assets/images/circum_linkedin.png"
                :width="30"
                :height="30"
              />
              LinkedIn
            </a>
          </div>
        </div>
      </div>
    </div>
    <p class="text-sm font-thin text-center mb-8">
      © 2025 ATHOMES Realty. All rights reserved.
    </p>
  </div>
</template>
