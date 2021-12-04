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

        <div v-if="!messageFailed && !messageSent">
          <q-input
            class="q-mt-sm"
            v-model="name"
            type="text"
            label="Name"
            filled
          />
          <q-input
            class="q-mt-sm"
            v-model="email"
            type="email"
            label="Email"
            filled
          />
          <q-input
            class="q-mt-sm"
            v-model="subject"
            type="text"
            label="Subject"
            filled
          />
          <q-input
            class="q-mt-sm"
            v-model="message"
            type="textarea"
            label="Message"
            filled
          />
          <q-btn
            color="primary"
            icon="send"
            round
            size="20px"
            class="float-right q-mt-md q-pa-md"
            @click="sendMessage()"
          />
        </div>

        <div class="text-h6 text-center" v-if="messageFailed && !messageSent">
          Something went wrong. No worries! You can send us an email at
          <a
            target="_blank"
            :href="`mailto:info@bmcomputers.info?subject=${subject}&body=${message}`"
          >
            info@bmcomputers.info
          </a>
        </div>

        <div class="text-h6 text-center" v-if="!messageFailed && messageSent">
          Message sent successfully!
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import { defineComponent, ref } from "vue";
import { useQuasar } from "quasar";
import { sendMail } from "boot/sendMail";
export default defineComponent({
  setup() {
    const name = ref("");
    const email = ref("");
    const subject = ref("");
    const message = ref("");

    const quasar = useQuasar();

    const messageSent = ref(false);
    const messageFailed = ref(false);

    const sendMessage = () => {
      if (name.value && email.value && message.value && subject.value) {
        sendMail({
          name: name.value,
          sender: email.value,
          subject: subject.value,
          body: message.value,
        })
          .then(() => {
            quasar.notify({
              message: "Your message was sent!",
              color: "primary",
              position: "top-right",
              progress: true,
              timeout: 1500,
            });
            messageSent.value = true;
          })
          .catch(() => {
            messageFailed.value = true;
            quasar.notify({
              message: "Something went wrong 😔",
              color: "red-10",
              position: "top-right",
              progress: true,
              timeout: 1500,
            });
            return;
          });
      } else {
        quasar.notify({
          message: "Please enter all of the fields 🤦",
          color: "red-10",
          position: "top-right",
          progress: true,
          timeout: 1500,
        });
      }
    };

    return {
      name,
      email,
      subject,
      message,
      sendMessage,
      messageFailed,
      messageSent,
    };
  },
});
</script>
