<template>
  <div>
    <q-carousel
      v-if="$q.screen.gt.sm"
      v-model="slide"
      transition-prev="slide-right"
      transition-next="slide-left"
      swipeable
      animated
      padding
      autoplay
      infinite
      height="200px"
      class="shadow-2 rounded-borders"
    >
      <q-carousel-slide :name="1" class="column no-wrap">
        <div
          class="
            row
            fit
            justify-start
            items-center
            q-gutter-xl q-col-gutter
            no-wrap
            flex-center
          "
        >
          <q-img
            class="rounded-borders col-2"
            src="/images/brands/lenovo.png"
          />

          <q-img
            class="rounded-borders col-2"
            src="/images/brands/tplink.png"
          />

          <q-img class="rounded-borders col-2" src="/images/brands/intel.png" />

          <q-img class="rounded-borders col-2" src="/images/brands/invo.png" />
        </div>
      </q-carousel-slide>
      <q-carousel-slide :name="2" class="column no-wrap">
        <div
          class="
            row
            fit
            justify-start
            items-center
            q-gutter-xl q-col-gutter
            no-wrap
            flex-center
          "
        >
          <q-img class="rounded-borders col-2" src="/images/brands/asus.png" />

          <q-img class="rounded-borders col-2" src="/images/brands/msi.png" />

          <q-img class="rounded-borders col-2" src="/images/brands/hik.png" />

          <q-img class="rounded-borders col-2" src="/images/brands/amd.png" />
        </div>
      </q-carousel-slide>

      <q-carousel-slide :name="3" class="column no-wrap">
        <div
          class="
            row
            fit
            justify-start
            items-center
            q-gutter-xl q-col-gutter
            no-wrap
            flex-center
          "
        >
          <q-img class="rounded-borders col-2" src="/images/brands/zotac.png" />
          <q-img
            class="rounded-borders col-2"
            src="/images/brands/kingston.png"
          />
          <q-img
            class="rounded-borders col-1"
            width="150px"
            src="/images/brands/ryzen.png"
          />

          <div class="text-h6">and more...</div>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    return {
      slide: ref(1),
    };
  },
};
</script>
