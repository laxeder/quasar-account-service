<template>
  <q-drawer class="bg-primary" v-model="leftDrawerOpen" show-if-above elevated>
    <q-list>
      <q-item-label header class="text-primary">Menu da aplicação</q-item-label>

      <MDrawerItemComponent
        v-for="item in drawerItems"
        :key="item.title"
        v-bind="item"
      />
    </q-list>
  </q-drawer>
</template>

<script setup lang="ts">
import MDrawerItemComponent, {
  DrawerItemProps,
} from './MDrawerItemComponent.vue';

const leftDrawerOpen = defineModel('leftDrawerOpen', { type: Boolean });

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
</script>
