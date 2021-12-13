<template>
  <div
    class="fixed-top row bg-blur z-top no-shadow full-width q-pa-sm q-gutter-sm"
  >
    <q-space />

    <q-btn color="white" icon="menu" flat>
      <q-menu
        class="z-top"
        transition-show="jump-down"
        transition-hide="jump-up"
      >
        <q-list style="min-width: 100px">
          <q-item
            @click="services"
            class="text-center q-ma-sm"
            clickable
            v-close-popup
          >
            <q-item-section> Our services </q-item-section>
          </q-item>

          <q-item
            @click="about"
            class="text-center q-ma-sm"
            clickable
            v-close-popup
          >
            <q-item-section> Company info </q-item-section>
          </q-item>

          <q-item
            @click="contact"
            class="text-center q-ma-sm"
            clickable
            v-close-popup
          >
            <q-item-section> Contact us </q-item-section>
          </q-item>
        </q-list>
      </q-menu>
    </q-btn>
  </div>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  setup() {
    const menu = ref(true);

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
      menu,
      contact,
      services,
      about,
    };
  },
});
</script>

<style lang="scss" scoped>
a {
  text-decoration: none;
}
</style>
