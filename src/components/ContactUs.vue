<template>
  <section
    class="full-height q-mt-sm"
    :class="{ 'full-screen': $q.screen.gt.sm }"
  >
    <div class="full-height" :class="{ column: $q.screen.lt.md }">
      <div id="contact" class="column">
        <div class="text-h3 contact-header text-center poppins q-my-md">
          Contact us
        </div>

        <div v-if="$q.screen.lt.md" class="text-center" style="font-size: 13px">
          Call us on : 04/870 115 or send us an email at
          <a href="mailto:info.bmcomp@gmail.com" target="_blank"
            >info.bmcomp@gmail.com</a
          >
        </div>

        <div
          v-if="$q.screen.gt.sm"
          class="q-ma-md flex-center flex q-gutter-sm"
        >
          <q-card class="col-4 radius-16" style="width: 200px">
            <q-card-section class="text-center">
              <q-icon name="call" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              04/870 115
            </q-card-section>
          </q-card>

          <q-card class="col-4 radius-16" style="width: 200px">
            <q-card-section class="text-center">
              <q-icon name="place" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              Beit Mery
            </q-card-section>
          </q-card>

          <q-card class="col-4 radius-16" style="width: 200px">
            <q-card-section class="text-center">
              <q-icon name="email" size="40px" />
            </q-card-section>
            <q-card-section class="text-center contact-info">
              <a href="mailto:info.bmcomp@gmail.com" target="_blank"
                >info.bmcomp@gmail.com</a
              >
            </q-card-section>
          </q-card>
        </div>

        <div
          :class="{
            'q-pa-md ': $q.screen.lt.md,
            'q-pa-sm': $q.screen.gt.sm,
            'contact-padding': $q.screen.gt.sm,
          }"
        >
          <iframe
            class="q-mt-sm map radius-16 full-width"
            style="border: 0"
            height="325px"
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2778.0843604087877!2d35.60225051475151!3d33.86401938065755!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x151f3d290a5dc7b3%3A0xa367c03a7c1661d4!2sAl%20Birkeh!5e1!3m2!1sen!2sin!4v1638441728852!5m2!1sen!2sin"
            allowfullscreen
            loading="lazy"
          ></iframe>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
.contact-info {
  font-size: 15px;
  color: #ebedf0;
}

.contact-header {
  color: white;
}

.contact-padding {
  padding-left: 200px;
  padding-right: 200px;
}

@media (max-width: $breakpoint-xs-max) {
  .send-btn {
    padding: 15px;
    margin: 15px;
  }
}
</style>
