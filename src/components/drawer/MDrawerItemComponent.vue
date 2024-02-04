<template>
  <q-item clickable tag="a" target="_blank" :href="link">
    <q-item-section v-if="icon" avatar>
      <q-icon :name="icon" class="text-primary" />
    </q-item-section>

    <q-item-section>
      <q-item-label class="text-primary text-weight-medium">{{
        title
      }}</q-item-label>
      <q-item-label class="" style="opacity: 0.9" caption>{{
        caption
      }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script setup lang="ts">
export interface DrawerItemProps {
  title: string;
  caption?: string;
  link?: string;
  icon?: string;
}
withDefaults(defineProps<DrawerItemProps>(), {
  caption: '',
  link: '#',
  icon: '',
});
</script>
