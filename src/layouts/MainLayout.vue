<template>
  <q-layout view="lHh Lpr lFf">
    <m-header-component @toggle-left-drawer="toggleLeftDrawer" />

    <m-drawer-component v-model:leftDrawerOpen="leftDrawerOpen" />

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import MHeaderComponent from 'components/MHeaderComponent.vue';
import MDrawerComponent from 'components/drawer/MDrawerComponent.vue';

const leftDrawerOpen = ref(false);

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
