<template>
  <div class="full-screen bg-dark flex flex-center">
    <div class="absolute items-start blur q-pa-lg column">
      <q-img
        src="/images/logo2.png"
        alt="bmc logo"
        style="border-radius: 16px"
      />
      <div class="text-h4 q-mt-lg">Hardware, sofware and more....</div>

      <div class="flex flex-center">
        <q-btn label="About us" color="primary" @click="dialog = true" />
      </div>
    </div>
  </div>

  <!-- About dialog -->
  <q-dialog
    v-model="dialog"
    maximized
    transition-show="slide-up"
    transition-hide="slide-down"
  >
    <q-card class="bg-accent text-white">
      <q-bar>
        <q-space />

        <q-btn dense flat icon="close" v-close-popup>
          <q-tooltip class="bg-white text-primary">Close</q-tooltip>
        </q-btn>
      </q-bar>

      <q-card-section class="q-pt-none">
        <about-us />
      </q-card-section>
    </q-card>
  </q-dialog>
</template>

<script>
import { ref } from "vue";
import AboutUs from "./AboutUs.vue";

export default {
  components: {
    AboutUs,
  },
  setup() {
    return {
      dialog: ref(false),
    };
  },
};
</script>
