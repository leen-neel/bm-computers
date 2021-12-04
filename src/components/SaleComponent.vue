<template>
  <q-banner
    v-if="hasSale && isOpen"
    class="bg-info text-center q-my-md radius-16 q-pa-md"
    style="width: 80%"
  >
    <div class="text-h4 flex items-center">
      <q-badge color="negative" class="text-weight-bolder sales-badge">
        SPECIAL OFFER!
      </q-badge>
      <q-space />

      <q-btn color="white" icon="close" flat round @click="isOpen = false" />
    </div>

    <div class="text-h2 lobster">
      {{ heading }}
    </div>
    <p class="q-mt-sm">{{ description }}</p>
  </q-banner>
</template>

<script>
export default {
  props: {
    heading: String,
    description: String,
    hasSale: Boolean,
  },
  data() {
    return {
      isOpen: true,
    };
  },
};
</script>

<style lang="scss" scoped>
.sales-badge {
  position: relative;
  bottom: 30px;
  right: 20px;

  padding: 20px;
}
</style>
