<template>
  <q-header class="bg-primary" elevated>
    <q-toolbar>
      <q-btn
        flat
        dense
        round
        icon="menu"
        aria-label="Menu"
        @click="$emit('toggle-left-drawer')"
      />

      <q-toolbar-title>Serviço de contas</q-toolbar-title>

      <q-btn color="secondary" text-color="primary" @click="onLogin"
        >Entrar</q-btn
      >
    </q-toolbar>
  </q-header>
</template>

<script setup lang="ts">
import { useRouter } from 'vue-router';

defineEmits(['toggle-left-drawer']);

const router = useRouter();

function onLogin() {
  router.push('/login');
}
</script>
