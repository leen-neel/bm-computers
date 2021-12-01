<template>
  <section class="q-mt-lg q-pa-md">
    <div class="row">
      <div class="col-12">
        <div class="text-h3 text-center poppins q-mb-md">Contact us</div>
      </div>

      <div class="col-12 q-gutter-sm">
        <div class="q-ma-md flex-center flex q-gutter-sm">
          <q-card dark>
            <q-card-section class="flex flex-center">
              <q-icon name="call" size="40px" />
            </q-card-section>
            <q-card-section> +961-4-870-115 </q-card-section>
          </q-card>

          <q-card class="my-card">
            <q-card-section class="flex flex-center">
              <q-icon name="place" size="40px" />
            </q-card-section>
            <q-card-section> Beit Mery - Lebanon </q-card-section>
          </q-card>

          <q-card class="my-card">
            <q-card-section class="flex flex-center">
              <q-icon name="email" size="40px" />
            </q-card-section>
            <q-card-section> info@bmcomputers.info </q-card-section>
          </q-card>
        </div>

        <q-input v-model="name" type="text" label="Name" filled />
        <q-input v-model="email" type="email" label="Email" filled />
        <q-input v-model="subject" type="text" label="Subject" filled />

        <q-input v-model="message" type="textarea" label="Message" filled />
      </div>
    </div>
  </section>
</template>

<script>
import { defineComponent, ref } from "vue";
export default defineComponent({
  setup() {
    const name = ref("");
    const email = ref("");
    const subject = ref("");
    const message = ref("");

    return {
      name,
      email,
      subject,
      message,
    };
  },
});
</script>
