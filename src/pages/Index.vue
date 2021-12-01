<template>
  <q-page>
    <HeroSection />
  </q-page>
</template>

<script>
import HeroSection from "src/components/HeroSection.vue";

import { defineComponent } from "vue";

export default defineComponent({
  name: "PageIndex",
  components: {
    HeroSection,
  },
});
</script>
