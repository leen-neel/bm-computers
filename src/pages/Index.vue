<template>
  <q-page>
    <HeroSection />

    <AboutUs />

    <ContactUs />
  </q-page>
</template>

<script>
import AboutUs from "src/components/AboutUs.vue";
import ContactUs from "src/components/ContactUs.vue";
import HeroSection from "src/components/HeroSection.vue";

import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
  components: {
    HeroSection,
    AboutUs,
    ContactUs,
  },
});
</script>
