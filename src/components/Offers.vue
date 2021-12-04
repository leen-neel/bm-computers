<template>
  <section class="q-pa-md q-mt-md">
    <div class="flex">
      <q-space />
      <q-btn
        color="white"
        class="q-mr-sm"
        icon="close"
        @click="closeOffers"
        round
        flat
      />
    </div>

    <div>
      <div class="text-h3">Offer</div>
      <p class="q-mt-sm">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Impedit ducimus
        accusantium natus commodi fugiat nihil laboriosam odio quas tempora,
        cupiditate sint ullam id totam expedita temporibus voluptatibus facilis,
        enim ex!
      </p>
    </div>
  </section>
</template>

<script>
import { defineComponent } from "vue";
export default defineComponent({
  name: "Offers",

  emits: ["close-offers"],

  setup(props, { emit }) {
    const closeOffers = () => {
      emit("close-offers");
    };

    return {
      closeOffers,
    };
  },
});
</script>
