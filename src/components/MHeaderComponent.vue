<template>
  <q-header class="bg-primary" elevated>
    <q-toolbar>
      <q-btn
        flat
        dense
        round
        icon="menu"
        class="text-primary"
        aria-label="Menu"
        @click="$emit('toggle-left-drawer')"
      />

      <q-toolbar-title class="text-primary">Serviço de contas</q-toolbar-title>

      <q-btn
        flat
        @click="$q.dark.toggle"
        icon="brightness_4"
        class="text-primary"
      />

      <q-btn class="bg-secondary text-secondary" @click="onLogin">Entrar</q-btn>
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
