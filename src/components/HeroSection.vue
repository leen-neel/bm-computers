<template>
  <div
    class="full-screen flex flex-center q-pa-md q-gutter-lg"
    :class="{ column: $q.screen.lt.md, flex: $q.screen.gt.sm }"
  >
    <q-img
      v-if="$q.screen.gt.sm"
      src="/images/logo.png"
      alt="bmc logo"
      class="radius-16 logo"
      style="width: 80%"
    />

    <q-img
      v-if="$q.screen.lt.md"
      src="/images/logo-mobile.png"
      alt="bmc logo"
      class="radius-16 logo"
      style="width: 80%"
    />

    <div class="full-width">
      <ProductsSlider />
    </div>

    <SaleComponent
      heading="Holiday sale"
      description="Get 69% off"
      :hasSale="false"
      @open="offers = true"
    />
  </div>

  <Offers v-if="offers" @close-offers="offers = false" />

  <!-- About dialog -->
  <q-dialog
    v-model="aboutDialog"
    maximized
    transition-show="slide-up"
    transition-hide="slide-down"
  >
    <q-card class="bg-section">
      <div class="flex">
        <q-space />
        <q-btn size="15px" flat icon="close" round v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
        </q-btn>
      </div>

      <q-card-section class="q-pt-none flex flex-center">
        <AboutUs />
      </q-card-section>
    </q-card>
  </q-dialog>

  <!-- Contact dialog -->
  <q-dialog
    v-model="contactDialog"
    transition-show="slide-left"
    transition-hide="slide-left"
  >
    <q-card class="bg-section radius-16">
      <div class="flex">
        <q-space />
        <q-btn size="15px" flat icon="close" round v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
        </q-btn>
      </div>

      <q-card-section class="q-pt-none flex flex-center">
        <ContactUs />
      </q-card-section>
    </q-card>
  </q-dialog>

  <!-- Contact dialog -->
  <q-dialog
    v-model="locateDialog"
    transition-show="fade"
    transition-hide="fade"
  >
    <q-card class="bg-section radius-16" style="width: 90vw">
      <div class="flex">
        <q-space />
        <q-btn size="15px" flat icon="close" round v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
        </q-btn>
      </div>

      <LocateUs />
    </q-card>
  </q-dialog>
</template>

<script>
import { ref } from "vue";
import AboutUs from "./AboutUs.vue";
import ContactUs from "./ContactUs.vue";
import LocateUs from "./LocateUs.vue";
import SaleComponent from "./SaleComponent.vue";
import Offers from "./Offers.vue";
import ProductsSlider from "./ProductsSlider.vue";

export default {
  components: {
    AboutUs,
    ContactUs,
    LocateUs,
    SaleComponent,
    Offers,
    ProductsSlider,
  },
  setup() {
    return {
      aboutDialog: ref(false),
      contactDialog: ref(false),
      locateDialog: ref(false),
      offers: ref(false),
    };
  },
};
</script>

<style lang="scss" scoped>
@media (max-width: $breakpoint-xs-max) {
  .logo {
    width: 500px;
  }
}
</style>
