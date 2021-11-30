<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "MainLayout",
});
</script>

<style lang="scss" scoped>
.header {
  background-color: rgba(0, 0, 0, 0);
  backdrop-filter: blur(7px);
}
</style>
