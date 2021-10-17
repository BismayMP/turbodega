<template>
  <q-item clickable tag="a" :href="link" class="drawer-link">
    <q-item-section v-if="icon" avatar class="drawer-icon">
      <q-icon :name="icon" />
    </q-item-section>
    <q-item-section>
      <q-item-label class="drawer-text">{{ title }}</q-item-label>
    </q-item-section>
  </q-item>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'DrawerLink',
  props: {
    title: {
      type: String,
      required: true,
    },
    link: {
      type: String,
      default: '#',
    },

    icon: {
      type: String,
      default: '',
    },
  },
});
</script>
