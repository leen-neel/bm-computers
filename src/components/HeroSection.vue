<template>
  <div class="full-screen column bg-dark flex flex-center q-pa-md">
    <q-img
      src="/images/logo2.png"
      alt="bmc logo"
      style="border-radius: 16px; width: 600px"
    />

    <div class="column">
      <div class="text-h4 text-center q-mt-md">
        Hardware, sofware and more....
      </div>
      <div class="flex flex-center q-mt-md q-gutter-sm">
        <q-btn
          label="About us"
          color="primary"
          @click="aboutDialog = true"
          icon="storefront"
        />

        <q-btn
          label="Contact us"
          color="primary"
          @click="contactDialog = true"
          icon="email"
        />

        <q-btn
          label="Locate us"
          color="primary"
          @click="locateDialog = true"
          icon="place"
        />
      </div>
    </div>
  </div>

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
    maximized
    transition-show="slide-left"
    transition-hide="slide-left"
  >
    <q-card class="bg-section">
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
    maximized
    transition-show="fade"
    transition-hide="fade"
  >
    <q-card class="bg-section">
      <div class="flex">
        <q-space />
        <q-btn size="15px" flat icon="close" round v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
        </q-btn>
      </div>

      <q-card-section class="q-pt-none flex flex-center">
        <LocateUs />
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script>
import { ref } from "vue";
import AboutUs from "./AboutUs.vue";
import ContactUs from "./ContactUs.vue";
import LocateUs from "./LocateUs.vue";

export default {
  components: {
    AboutUs,
    ContactUs,
    LocateUs,
  },
  setup() {
    return {
      aboutDialog: ref(false),
      contactDialog: ref(false),
      locateDialog: ref(false),
    };
  },
};
</script>
