<template>
  <q-layout view="lHh Lpr lFf">
    <q-header v-show="true" elevated class="bg-trasnparent show-collapse">
      <q-toolbar>
        <q-btn flat @click="drawer = !drawer" round dense icon="menu" />
        <q-toolbar-title>TURBODEGA</q-toolbar-title>
      </q-toolbar>
    </q-header>

    <q-drawer
      v-model="drawer"
      show-if-above
      :breakpoint="960"
      class="drawer-root"
    >
      <div class="bg-transparent">
        <div class="text-weight-bold flex justify-center">
          <h4>TURBODEGA</h4>
        </div>
      </div>
      <q-list>
        <DrawerLink v-for="link in links" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page- algin-start>
      <router-view />
    </q-page->
  </q-layout>
</template>

<script lang="ts">
import DrawerLink from 'components/DrawerLink.vue';

const linksList = [
  {
    title: 'Registro de ventas',
    icon: 'school',
    link: '/sales',
  },
  {
    title: 'Reporte de mi negocio',
    icon: 'code',
    link: '/my-store',
  },
  {
    title: 'Quiero comprar',
    icon: 'chat',
    link: '/store',
  },
  {
    title: 'Mi inventario',
    icon: 'record_voice_over',
    link: '/my-products',
  },
];

import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'MainLayout',
  components: {
    DrawerLink,
  },

  setup() {
    const drawer = ref(false);

    if (window.outerWidth > 1024) {
      drawer.value = false;
    }

    return {
      drawer,
      links: linksList,
      toggleDrawer() {
        drawer.value = !drawer.value;
      },
    };
  },
});
</script>
