<template>
  <!-- Desktop version -->
  <div
    v-if="$q.screen.gt.sm"
    class="flex column flex-center bg-image full-screen full-width"
  >
    <div class="flex flex-center">
      <div class="hero-text q-pa-md">
        <img
          src="https://cdn.discordapp.com/attachments/912888928749645896/920262842299588658/bmc_desktop.png"
          alt="bmc logo"
          class="radius-16 logo"
        />
      </div>
    </div>
  </div>

  <!-- Mobile version -->
  <div
    class="bg-image column flex flex-center full-screen full-width"
    v-if="$q.screen.lt.md"
  >
    <div class="hero-text q-pa-md">
      <img
        v-if="$q.screen.lt.md"
        src="https://cdn.discordapp.com/attachments/912888928749645896/919961927696932934/logo-mobile_small.png"
        alt="bmc logo"
        class="logo"
      />
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    const contact = () => {
      document.getElementById("contact").scrollIntoView({ behavior: "smooth" });
    };

    const services = () => {
      document
        .getElementById("services")
        .scrollIntoView({ behavior: "smooth" });
    };

    const about = () => {
      document.getElementById("about").scrollIntoView({ behavior: "smooth" });
    };

    return {
      contact,
      services,
      about,
    };
  },
};
</script>

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

.logo {
  width: 70vw;
}

@media (max-width: $breakpoint-xs-max) {
  .logo {
    width: 300px;
  }
}
</style>
