<template>
  <section id="about" class="q-mt-lg q-pa-md">
    <div :class="{ row: $q.screen.gt.sm }">
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

      <div
        class="col-xs-12 col-sm-6 col-md-5"
        :class="{ content: $q.screen.gt.sm }"
      >
        <p>
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

    <BrandsSlider />
  </section>
</template>

<script>
import BrandsSlider from "./BrandsSlider.vue";

export default {
  components: {
    BrandsSlider,
  },
};
</script>

<style lang="scss" scoped>
.content {
  margin-left: 50px;
  padding-top: 80px;
}
</style>
