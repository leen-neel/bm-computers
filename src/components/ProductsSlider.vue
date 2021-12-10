<template>
  <q-carousel
    v-model="slider"
    transition-prev="slide-right"
    transition-next="slide-left"
    swipeable
    animated
    padding
    autoplay
    infinite
    height="30vh"
    width="100%"
    class="shadow-2 rounded-borders bgc"
  >
    <q-carousel-slide :name="1" class="column no-wrap">
      <div
        class="
          row
          fit
          full-height
          items-center
          q-col-gutter
          no-wrap
          flex-center
        "
      >
        <q-img
          class="q-mx-xl col-1"
          src="/images/products/logitech_mouse.png"
        />

        <q-img class="q-mx-xl col-2" src="/images/products/samsung_ssd.png" />

        <q-img
          class="q-mx-xl col-1"
          src="/images/products/invo_batteries.png"
        />

        <q-img
          class="q-mx-xl col-2"
          width="250px"
          src="/images/products/thinkpad.png"
        />
      </div>
    </q-carousel-slide>
    <q-carousel-slide :name="2" class="column no-wrap">
      <div
        class="
          row
          fit
          full-height
          items-center
          q-col-gutter
          no-wrap
          flex-center
        "
      >
        <q-img class="q-mx-xl col-2" src="/images/products/repair.png" />

        <q-img
          class="q-mx-xl col-2"
          src="/images/products/computer-repair.png"
        />

        <q-img class="q-mx-xl col-1" src="/images/products/router.png" />

        <q-img class="q-mx-xl col-1" src="/images/products/ups.png" />
      </div>
    </q-carousel-slide>
  </q-carousel>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      slider: ref(1),
    };
  },
};
</script>

<style lang="scss" scoped>
.bgc {
  background-color: #81a1c1;
}
</style>
