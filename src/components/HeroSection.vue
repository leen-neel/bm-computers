<template>
  <!-- Desktop version -->
  <div
    v-if="$q.screen.gt.sm"
    class="flex flex-center bg-image full-screen full-width"
  >
    <div class="row">
      <div class="col-5 hero-text q-gutter-sm q-ml-lg q-pa-md flex column">
        <div class="text-h4">BM Computers</div>
        <div class="text-h6">
          BM Computers is a Beit Mery based and standard computer repair Store.
          We are a computer repair company that is set to compete in the highly
          competitive computer repair services industry.
        </div>

        <q-btn
          color="primary"
          icon="south"
          label="Learn more"
          class="cta radius-16"
        />
      </div>

      <q-space />

      <img
        src="/images/logo.png"
        alt="bmc logo"
        class="radius-16 logo col-6 q-mr-lg"
      />
    </div>
  </div>

  <!-- Mobile version -->
  <div
    class="bg-image flex flex-center full-screen full-width"
    v-if="$q.screen.lt.md"
  >
    <q-img
      v-if="$q.screen.lt.md"
      src="/images/logo-mobile.png"
      alt="bmc logo"
      class="logo"
    />

    <div class="hero-text q-ma-lg q-pa-md flex column">
      <div class="text-h4">BM Computers</div>
      <div class="text-h6">
        BM Computers is a Beit Mery based and standard computer repair Store. We
        are a computer repair company that is set to compete in the highly
        competitive computer repair services industry.
      </div>

      <q-btn
        color="primary"
        icon="south"
        label="Learn more"
        class="q-py-md q-mt-sm radius-16"
      />
    </div>
  </div>
</template>

<style lang="scss" scoped>
.bg-image {
  background: url("/bgs/hero.svg") no-repeat bottom / cover;
  width: 100%;
}

.hero-text {
  background: rgba(129, 161, 193, 0.4);
  box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.37);
  backdrop-filter: blur(14.5px);
  -webkit-backdrop-filter: blur(14.5px);
  border-radius: 10px;
}

.cta {
  width: 20vw;
  padding: 20px 50px;
  font-weight: 900;
  font-size: medium;
}

@media (max-width: $breakpoint-xs-max) {
  .logo {
    width: 500px;
  }
}
</style>
