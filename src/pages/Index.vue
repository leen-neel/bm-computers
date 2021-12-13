<template>
  <q-page>
    <NavBar v-if="$q.screen.gt.sm" />
    <NavBarMobile v-if="$q.screen.lt.md" />

    <HeroSection />

    <div id="services" class="spacer layer q-mt-xl"></div>
    <Services />
    <div class="spacer rotate-180 layer q-mb-xl"></div>

    <AboutUs />

    <ContactUs />
  </q-page>
</template>

<script>
import AboutUs from "src/components/AboutUs.vue";
import ContactUs from "src/components/ContactUs.vue";
import HeroSection from "src/components/HeroSection.vue";
import NavBar from "src/components/NavBar.vue";
import NavBarMobile from "src/components/NavBarMobile.vue";
import Services from "src/components/Services.vue";

import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
  components: {
    HeroSection,
    AboutUs,
    ContactUs,
    NavBar,
    NavBarMobile,
    Services,
  },
});
</script>
