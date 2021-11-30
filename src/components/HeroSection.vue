<template>
  <!-- Rendered on desktop -->
  <div class="full-screen bg-dark row q-pa-xl">
    <div class="col-6 heroPos">
      <q-img
        src="/images/cool.png"
        spinner-color="primary"
        spinner-size="82px"
        style="border-radius: 16px"
      />
      <!-- <p class="text-h6 q-mt-sm">We manage hardware, software and more....</p> -->
      <q-btn
        type="a"
        color="primary"
        no-caps
        class="cta q-mt-lg"
        label="Learn more"
        icon-right="arrow_forward"
      />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "HeroSection",
});
</script>

<style lang="scss" scoped>
.heroPos {
  position: absolute;
  left: 5%;
  top: 30%;
}

.cta {
  padding: 16px 40px;
  border-radius: 8px;
  font-size: 18px;
  font-weight: 700;

  display: flex;
  align-items: center;
  justify-content: center;

  max-height: 56px;
  max-width: 273px;
}
</style>
