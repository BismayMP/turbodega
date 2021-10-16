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
        <EssentialLink v-for="link in links" :key="link.title" v-bind="link" />
      </q-list>
    </q-drawer>

    <q-page-container>
      <q-page padding>
        <p v-for="n in 15" :key="n">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugit nihil
          praesentium molestias a adipisci, dolore vitae odit, quidem
          consequatur optio voluptates asperiores pariatur eos numquam rerum
          delectus commodi perferendis voluptate?
        </p>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import EssentialLink from 'components/EssentialLink.vue';

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
    EssentialLink,
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
