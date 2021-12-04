<template>
  <q-banner
    v-if="hasSale"
    class="bg-info text-center full-width q-ma-md radius-16 q-pa-md"
  >
    <div class="text-h2">{{ heading }}</div>
    <p>{{ description }}</p>
  </q-banner>
</template>

<script>
export default {
  props: {
    heading: String,
    description: String,
    hasSale: Boolean,
  },
};
</script>
