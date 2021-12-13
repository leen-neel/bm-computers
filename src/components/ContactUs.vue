<template>
  <section class="q-mt-sm" :class="{ 'full-screen': $q.screen.gt.sm }">
    <div class="full-height row" :class="{ column: $q.screen.lt.md }">
      <div
        id="contact"
        class="column"
        :class="{ bg: $q.screen.gt.sm, 'col-6 ': $q.screen.gt.sm }"
      >
        <div class="text-h3 contact-header text-center poppins q-my-md">
          Contact us
        </div>

        <div v-if="$q.screen.lt.md" class="text-center" style="font-size: 13px">
          Call us on : 04/870 115 or send us an Email
        </div>

        <div
          v-if="$q.screen.gt.sm"
          class="q-ma-md flex-center flex q-gutter-sm"
        >
          <q-card class="col-4 bg-blur radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="call" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              04/870 115
            </q-card-section>
          </q-card>

          <q-card class="col-4 bg-blur radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="place" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              Beit Mery
            </q-card-section>
          </q-card>

          <q-card class="col-4 bg-blur radius-16" style="width: 110px">
            <q-card-section class="text-center">
              <q-icon name="email" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              Email
            </q-card-section>
          </q-card>
        </div>

        <div
          :class="{ 'q-pa-md ': $q.screen.lt.md, 'q-pa-sm': $q.screen.gt.sm }"
        >
          <iframe
            class="q-mt-sm map radius-16 full-width"
            style="border: 0"
            height="500px"
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2778.0843604087877!2d35.60225051475151!3d33.86401938065755!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x151f3d290a5dc7b3%3A0xa367c03a7c1661d4!2sAl%20Birkeh!5e1!3m2!1sen!2sin!4v1638441728852!5m2!1sen!2sin"
            allowfullscreen
            loading="lazy"
          ></iframe>
        </div>
      </div>

      <div
        class="column q-pa-lg"
        :class="{ 'col-6 ': $q.screen.gt.sm, 'xl-mt': $q.screen.gt.sm }"
      >
        <div v-if="!messageFailed && !messageSent">
          <q-input
            class="q-mt-sm"
            v-model="name"
            type="text"
            label="Name"
            filled
            placeholder="Your name"
            :loading="isLoading"
          />
          <q-input
            class="q-mt-sm"
            v-model="email"
            type="email"
            label="Email"
            placeholder="example@test.com"
            filled
            :loading="isLoading"
          />
          <q-input
            class="q-mt-sm"
            v-model="subject"
            type="text"
            label="Subject"
            placeholder="Fix my pc!"
            filled
            :loading="isLoading"
          />
          <q-input
            class="q-mt-sm"
            v-model="message"
            type="textarea"
            label="Message"
            placeholder="Lorem ipsum dolor "
            filled
            :loading="isLoading"
          />
          <q-btn
            color="primary"
            icon="send"
            label="Send"
            size="15px"
            class="float-right q-mt-md send-btn radius-16"
            @click="sendMessage()"
            :disable="disabled || isLoading"
          />
        </div>

        <div class="text-h6 text-center" v-if="messageFailed && !messageSent">
          Something went wrong. No worries! You can send us an email at
          <a
            target="_blank"
            :href="`mailto:info.bmcomp@gmail.com?subject=${subject}&body=${message}`"
          >
            info.bmcomp@gmail.com
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
      let re =
        /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;

      return !(
        name.value &&
        email.value &&
        subject.value &&
        message.value &&
        re.test(email.value)
      );
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
  color: #ebedf0;
}

.contact-header {
  color: white;
}

.xl-mt {
  margin-top: 235px;
}

.bg {
  background: url("/bgs/poly.svg") no-repeat bottom / cover;
}

.send-btn {
  padding: 20px 50px;
}
</style>
