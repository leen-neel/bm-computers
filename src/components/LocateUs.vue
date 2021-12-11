<template>
  <section
    class="q-mt-lg q-pa-md"
    :class="{
      row: $q.screen.gt.sm,
      column: $q.screen.lt.md,
      'full-screen': $q.screen.gt.sm,
    }"
  >
    <div class="col-6">
      <div class="text-h3 text-center poppins q-mb-md">Locate us</div>

      <div class="flex flex-center">
        <q-card
          class="text-center radius-16"
          :class="{ 'full-width': $q.screen.lt.md }"
          style="width: 25vw"
        >
          <q-card-section>
            Beit Mery Souq
            <br />
            Al Birkeh Roundabout
            <br />
            Facing Shaaya Hypermarket
          </q-card-section>
        </q-card>
      </div>
    </div>

    <div class="flex flex-center col-6">
      <iframe
        class="q-mt-sm map radius-16 full-width"
        style="border: 0"
        height="500px"
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2778.0843604087877!2d35.60225051475151!3d33.86401938065755!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x151f3d290a5dc7b3%3A0xa367c03a7c1661d4!2sAl%20Birkeh!5e1!3m2!1sen!2sin!4v1638441728852!5m2!1sen!2sin"
        allowfullscreen
        loading="lazy"
      ></iframe>
    </div>
  </section>
</template>

<style lang="scss" scoped>
@media (max-width: $breakpoint-xs-max) {
  .map {
    width: 300px;
  }
}
</style>
