<template>
  <section class="q-mt-lg q-pa-md">
    <div class="row">
      <div class="col-xs-12 col-sm-6 col-md-6">
        <div class="text-h3 poppins q-mb-md">About us</div>

        <q-img
          src="/images/store.jpg"
          class="q-my-md radius-16 full-width"
          height="500px"
          width="300px"
          spinner-color="primary"
          spinner-size="82px"
        />
      </div>

      <div class="col-xs-12 col-sm-6 col-md-4 q-ml-lg">
        <p style="padding-top: 80px">
          BM Computers is a Beit Mery based and standard computer repair Store.
          We are a computer repair company that is set to compete in the highly
          competitive computer repair services industry.
        </p>

        <p>
          BM Computers, will offer all aspect of computer repair services such
          as computer repair, computer cloning, computer maintenance, and
          everything that relates to computer hardware et al.
        </p>

        <p>
          Our business goal is to become one of the computer repair company in
          the area and we will make sure that we do all we can to compete
          favorably with leaders in the industry.
        </p>

        <p>
          At BM Computers, our client’s best interest will always come first,
          and everything we do will be guided by our values and professional
          ethics. We will ensure that we hold ourselves accountable to the
          highest standards by meeting our client’s needs precisely and
          completely.
        </p>
      </div>
    </div>

    <div>
      <q-carousel
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

            <q-img
              class="rounded-borders col-2"
              src="/images/brands/intel.png"
            />

            <q-img
              class="rounded-borders col-2"
              src="/images/brands/invo.png"
            />
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
            <q-img
              class="rounded-borders col-2"
              src="/images/brands/asus.png"
            />

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
            <q-img
              class="rounded-borders col-2"
              src="/images/brands/zotac.png"
            />
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
  </section>
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
