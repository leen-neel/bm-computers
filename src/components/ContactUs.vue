<template>
  <section class="q-mt-lg q-pa-md">
    <div class="column">
      <div class="col-12">
        <div class="text-h3 text-center poppins q-mb-md">Contact us</div>
      </div>

      <div class="column flex">
        <div
          v-if="$q.screen.gt.sm"
          class="q-ma-md flex-center flex q-gutter-sm"
        >
          <q-card class="col-4 radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="call" size="40px" />
            </q-card-section>
            <q-card-section class="text-center text-bold contact-info">
              04/870 115
            </q-card-section>
          </q-card>

          <q-card class="col-4 radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="place" size="40px" />
            </q-card-section>
            <q-card-section class="text-center text-bold contact-info">
              Beit Mery
            </q-card-section>
          </q-card>

          <q-card class="col-4 radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="email" size="40px" />
            </q-card-section>
            <q-card-section class="text-center text-bold contact-info">
              Email
            </q-card-section>
          </q-card>
        </div>

        <div v-if="$q.screen.lt.md" class="text-center" style="font-size: 13px">
          Call us on : 04/870 115 or send us an Email
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
            :disable="disabled || !isLoading"
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
import { defineComponent, ref, computed } from "vue";
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
    const isLoading = ref(false);

    const disabled = computed(() => {
      return name.value && email.value && subject.value && message.value;
    });

    const sendMessage = () => {
      if (name.value && email.value && message.value && subject.value) {
        isLoading.value = true;
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
            isLoading.value = false;
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
      isLoading,
      disabled,
    };
  },
});
</script>

<style lang="scss" scoped>
.contact-info {
  font-size: 15px;
}
</style>
