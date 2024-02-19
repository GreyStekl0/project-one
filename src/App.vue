<script setup>

import VHeader from "@/components/VHeader.vue";
import VFooter from "@/components/VFooter.vue";
import VPromo from "@/components/VPromo.vue";
import VWeb from "@/components/VWeb.vue";
import VProjects from "@/components/VProjects.vue";
import VTech from "@/components/VTech.vue";
import VFeedack from "@/components/VFeedack.vue";
</script>

<template>
  <v-header />
  <main>
    <v-promo />
    <v-web />
    <v-projects />
    <v-tech />
    <v-feedack />

  </main>
  <v-footer />
</template>

<style scoped>

</style>
