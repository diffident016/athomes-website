<template>
  <v-app>
    <NuxtLoadingIndicator />
    <div class="h-screen relative">
      <div
        v-if="$vuetify.display.lgAndUp"
        class="relative main d-flex w-100 h-100"
      >
        <div style="height: 100vh; width: 40%">
          <p class="pa-16" style="font-family: Poppins; font-size: 14px">
            HOME
          </p>
        </div>
        <div
          style="
            background-image: linear-gradient(
              rgba(255, 255, 255, 1),
              rgba(255, 255, 255, 0)
            );
            top: 68px;
            height: 40%;
          "
          class="w-100 position-absolute"
        ></div>

        <div
          style="height: 100vh; width: 60%"
          class="d-flex flex-column justify-center"
        >
          <div style="height: 8%"></div>
          <div
            style="max-width: max-content"
            class="d-flex flex-row align-center ga-4"
          >
            <img
              src="~/assets/images/athomes.png"
              :width="64"
              :height="64"
              class="mb-2"
            />
            <h1 class="header">ATHOMES</h1>
          </div>
          <div
            style="max-width: 380px"
            class="subheader d-flex flex-column w-100 align-center justify-center"
          >
            <p>a place where you truly</p>
            <p>feel at home!</p>
            <div class="d-flex flex-column align-center justify-center mt-10">
              <p class="coming">Coming soon</p>
              <div
                class="d-flex flex-row align-center justify-center ga-4 mt-4"
              >
                <img
                  class="cursor-pointer"
                  src="~/assets/images/circum_facebook.png"
                  :width="30"
                  :height="30"
                  @click="onClick('https://www.fb.com/athomescdorecruitement')"
                />
                <img
                  class="cursor-pointer"
                  src="~/assets/images/circum_linkedin.png"
                  :width="30"
                  :height="30"
                  @click="onClick('linkedin.com')"
                />
              </div>
            </div>
          </div>
        </div>
      </div>
      <div
        v-if="$vuetify.display.mdAndDown"
        style="height: 100vh; width: 100%"
        class="d-flex flex-column justify-center align-center"
      >
        <div style="height: 10%"></div>
        <div class="d-flex flex-row align-center ga-4">
          <img
            src="~/assets/images/athomes.png"
            :width="48"
            :height="48"
            class="mb-2"
          />
          <h1 style="font-size: 48px" class="header">ATHOMES</h1>
        </div>
        <div style="font-size: 22px" class="subheader d-flex flex-column">
          <p class="px-4">a place where you truly</p>
          <p class="text-center">feel at home!</p>
        </div>
        <div class="d-flex flex-column align-center justify-center mt-10">
          <p class="coming">Coming soon</p>
          <div class="d-flex flex-row align-center justify-center ga-4 mt-4">
            <img
              class="cursor-pointer"
              src="~/assets/images/circum_facebook.png"
              :width="30"
              :height="30"
              @click="onClick('https://www.fb.com/athomescdorecruitement')"
            />
            <img
              class="cursor-pointer"
              src="~/assets/images/circum_linkedin.png"
              :width="30"
              :height="30"
              @click="onClick('linkedin.com')"
            />
          </div>
        </div>
      </div>
      <footer style="position: absolute; bottom: 20px" class="w-100">
        <p class="footer">© 2024 by ATHOMES</p>
      </footer>
    </div>
  </v-app>
</template>

<script setup lang="ts">
function onClick(url: any) {
  window.location = url;
}
</script>

<style>
html {
  overflow-y: auto;
}
.main {
  background: url("/assets/images/background.png") no-repeat center center fixed;
  background-size: cover;
  background-size: 100% 100%;
}

.header {
  font-family: "Poppins";
  font-size: 64px;
  color: #221e1f;
}

.subheader {
  font-family: "Poppins-Light";
  font-size: 26px;
  color: #221e1f;
  font-weight: lighter;
  line-height: 40px;
}

.coming {
  font-family: "QwitcherGrypen";
  font-size: 50px;
  color: #221e1f;
}

.footer {
  font-family: "Poppins-Light";
  font-size: 14px;
  color: #221e1f;
  font-weight: lighter;
  text-align: center;
}
</style>
