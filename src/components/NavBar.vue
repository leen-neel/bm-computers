<template>
  <div class="bg-blur z-top no-shadow fixed-top row q-pa-sm q-gutter-sm">
    <q-space />

    <q-btn flat label="Our Services" @click="services" />
    <q-btn flat label="Conpany info" @click="about" />
    <q-btn flat label="Contact us" @click="contact" />
  </div>
</template>

<script>
export default {
  setup() {
    const contact = () => {
      document.getElementById("contact").scrollIntoView({ behavior: "smooth" });
    };

    const services = () => {
      document
        .getElementById("services")
        .scrollIntoView({ behavior: "smooth" });
    };

    const about = () => {
      document.getElementById("about").scrollIntoView({ behavior: "smooth" });
    };

    return {
      contact,
      services,
      about,
    };
  },
};
</script>
