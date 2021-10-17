<template>
  <q-page class="row page-container">
    <UserWidget :name="`Yulisa Torres`" :venta="245.0"></UserWidget>
    <product-list />
  </q-page>
</template>

<script lang="ts">
import UserWidget from 'components/UserComponent.vue';
import ProductList from 'components/ProductListComponent.vue';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'PageIndex',
  components: { UserWidget, ProductList },
});
</script>
