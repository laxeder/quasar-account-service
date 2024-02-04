<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-primary" elevated>
      <q-toolbar>
        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
        />

        <q-toolbar-title>Serviço de contas</q-toolbar-title>

        <q-btn color="secondary" text-color="primary" @click="onLogin"
          >Entrar</q-btn
        >
      </q-toolbar>
    </q-header>

    <q-drawer v-model="leftDrawerOpen" show-if-above bordered>
      <q-list>
        <q-item-label header>Menu da aplicação</q-item-label>

        <EssentialLink
          v-for="item in drawerItems"
          :key="item.title"
          v-bind="item"
        />
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import EssentialLink, {
  DrawerItemProps,
} from 'components/DrawerItemComponent.vue';
import { useRouter } from 'vue-router';

const drawerItems: DrawerItemProps[] = [
  {
    title: 'Documentação',
    caption: 'README.md',
    icon: 'school',
    link: 'https://github.com/laxeder/quasar-account-service/grob/main/README.md',
  },
  {
    title: 'Github',
    caption: 'github.com/laxeder/quasar-account-service',
    icon: 'code',
    link: 'https://github.com/laxeder/quasar-account-service',
  },
  {
    title: 'Criador',
    caption: 'github.com/laxeder',
    icon: 'person',
    link: 'https://github.com/laxeder',
  },
];

const leftDrawerOpen = ref(false);
const router = useRouter();

function onLogin() {
  router.push('/login');
}

function toggleLeftDrawer() {
  leftDrawerOpen.value = !leftDrawerOpen.value;
}
</script>
