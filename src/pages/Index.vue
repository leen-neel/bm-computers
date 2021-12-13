<template>
  <q-page>
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
import Services from "src/components/Services.vue";

import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
  components: {
    HeroSection,
    AboutUs,
    ContactUs,

    Services,
  },
});
</script>
